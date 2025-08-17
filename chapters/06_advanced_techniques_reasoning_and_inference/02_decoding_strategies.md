# 6.2 Decoding Strategies: How LLMs Choose Their Words

When a Large Language Model generates text, it doesn't write whole sentences at once. It predicts the next word (or "token") based on the sequence of words that came before it. The method it uses to select that next word is called a **decoding strategy**.

The choice of decoding strategy has a massive impact on the quality of the output. A simple strategy might lead to repetitive or nonsensical text, while a more advanced one can produce creative, coherent, and contextually relevant results.

Let's explore the most common strategies.

## Greedy Search

Greedy search is the simplest decoding strategy. At each step, the model selects the single word that has the highest probability according to its calculations.

*   **How it works**: If the model is predicting the next word after "The cat sat on the," and the word "mat" has a 40% probability, "rug" has 30%, and "floor" has 15%, greedy search will always choose "mat."
*   **Pros**: It's fast, computationally cheap, and often produces reasonable results for very short, factual sentences.
*   **Cons**: It's short-sighted. The best word at one step might lead to a dead-end or a nonsensical sentence later on. A slightly less probable word at the current step could have opened up a much better overall sentence structure. This often leads to repetitive and unnatural-sounding text.

## Beam Search

Beam search is an improvement over greedy search that considers a wider context. Instead of just picking the single best word at each step, it keeps track of a fixed number of the most probable sequences of words. This number is known as the **beam width** (or `k`).

*   **How it works**: If the beam width is 3, the model will keep track of the three most likely word sequences at all times. At each step, it considers all possible next words for each of the three sequences, calculates the total probability of the new, longer sequences, and again keeps only the top three.
*   **Pros**: It produces much more fluent and coherent text than greedy search because it explores multiple possibilities and can avoid the short-sighted mistakes of the greedy approach. It is often used in tasks like machine translation where fluency is key.
*   **Cons**: It is more computationally expensive than greedy search. It also has a tendency to favor safe, high-probability, and sometimes generic sentences, and can still get stuck in repetitive loops, though less often than greedy search.

### A Deeper Dive: An Example of Beam Search

Let's walk through a concrete example to see how it works.

*   **Goal**: Generate a sequence of two words.
*   **Input**: "The dog ran"
*   **Beam Width (k)**: 2

#### Step 1: The First Word

The model looks at the input "The dog ran" and predicts the probabilities for the next word:
*   `across`: 0.4
*   `fast`: 0.3
*   `to`: 0.15
*   `down`: 0.1
*   ... (other words)

Since our beam width is 2, we keep the top 2 most likely sequences (or "beams"):
1.  **Beam 1**: "The dog ran across" (Probability: 0.4)
2.  **Beam 2**: "The dog ran fast" (Probability: 0.3)

A greedy search would have committed to "across" and never looked back. Beam search, however, keeps the second-best option "fast" in play.

#### Step 2: The Second Word

Now, the model predicts the next word for *both* beams independently.

**For Beam 1 ("...across"):**
*   `the`: 0.5
*   `a`: 0.2
*   `...`

**For Beam 2 ("...fast"):**
*   `and`: 0.6
*   `to`: 0.3
*   `...`

Next, we calculate the total probability of the new, two-word sequences by multiplying the probability of the beam with the probability of the new word.

**Candidate Sequences:**
1.  From Beam 1: "The dog ran across **the**" -> Prob = 0.4 * 0.5 = **0.20**
2.  From Beam 1: "The dog ran across **a**" -> Prob = 0.4 * 0.2 = 0.08
3.  From Beam 2: "The dog ran fast **and**" -> Prob = 0.3 * 0.6 = **0.18**
4.  From Beam 2: "The dog ran fast **to**" -> Prob = 0.3 * 0.3 = 0.09

We now have four candidate sequences. To maintain our beam width of 2, we again select the top 2 from this list:

1.  **"The dog ran across the" (Total Probability: 0.20)**
2.  **"The dog ran fast and" (Total Probability: 0.18)**

#### Conclusion

After two steps, our final candidate sequences are "The dog ran across the" and "The dog ran fast and". The model would output the top sequence: **"The dog ran across the"**.

Notice that the second-best option, "fast and", had a higher probability (0.18) than the discarded "across a" (0.08). If "fast and" had been followed by a very high-probability word in the next step, it could have overtaken "across the". Greedy search would have missed this possibility entirely. By keeping multiple hypotheses, beam search explores the search space more thoroughly, leading to more optimal and human-like sequences.

> **Note**: In a real-world scenario, models use log probabilities. Instead of multiplying probabilities, they add the log probabilities, which is numerically more stable and avoids the risk of numbers becoming too small ("arithmetic underflow"). The core principle of expanding and pruning beams remains the same.

## Sampling Strategies

While beam search aims to find a high-probability output, sometimes we want more creativity or diversity. This is where sampling comes in.

### Top-K Sampling

In Top-K sampling, the model considers only the top `K` most likely words for the next step, and then it **samples** from that smaller pool (meaning it picks one randomly, weighted by their probabilities).

*   **How it works**: If `K=10`, the model lists the 10 most probable next words, ignores all others, and then picks one from that list.
*   **Pros**: This prevents the model from picking very strange or nonsensical words that have a tiny but non-zero probability, making the output more coherent than pure random sampling.
*   **Cons**: The size of the top `K` list is fixed. For some contexts, the true number of reasonable next words might be very large, and for others, it might be very small. A fixed `K` isn't always optimal.

### Top-P (Nucleus) Sampling

Top-P, or Nucleus Sampling, is a more dynamic approach. Instead of picking a fixed number of words (`K`), it picks a list of words whose combined probability is at least `P`.

*   **How it works**: If `P=0.95`, the model lists the most probable words in descending order and keeps adding them to the list until their cumulative probability exceeds 95%. Then, it samples from this dynamically-sized list.
*   **Pros**: This is often considered the best of both worlds. When the model is very certain about the next word (e.g., after "The Eiffel Tower is in"), the list will be very small, leading to a safe choice. When the model is uncertain and many words are plausible, the list will be larger, allowing for more creativity.
*   **Cons**: It requires careful tuning of the `P` value to get the desired level of creativity vs. coherence.