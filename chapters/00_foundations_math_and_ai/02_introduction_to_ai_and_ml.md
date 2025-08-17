# 0.2 Introduction to AI and Machine Learning

At its core, Artificial Intelligence (AI) is a broad field of computer science dedicated to creating systems that can perform tasks that typically require human intelligence. Machine Learning (ML) is a subset of AI that focuses on a specific approach: building systems that can learn from data.

Instead of being explicitly programmed with rules, an ML model identifies patterns in data and makes predictions or decisions based on those patterns. The two most fundamental paradigms for this learning process are Supervised and Unsupervised Learning.

## Supervised vs. Unsupervised Learning

Imagine you are teaching a child to recognize different types of fruit. The way you teach them can be supervised or unsupervised.

### Supervised Learning: Learning with a Teacher

**Supervised Learning** is like showing the child flashcards.

- You show them a picture of an apple (**input data**).
- You tell them, "This is an apple" (**label**).
- You show them a picture of a banana (**input data**).
- You tell them, "This is a banana" (**label**).

After showing them hundreds of these labeled flashcards, the child (the model) learns to associate the features of the image with the correct name. Eventually, when you show them a new picture of an apple they've never seen before, they can correctly identify it as "apple."

**Core Idea:** The model learns from data that is **explicitly labeled** with the correct answers. It's "supervised" because a "teacher" (the labels) is guiding the learning process.

**Key Characteristics:**
*   **Data:** Labeled data (e.g., emails marked as "spam" or "not spam").
*   **Goal:** To predict a specific, known outcome or label.
*   **Common Tasks:**
    *   **Classification:** Predicting a category (e.g., Is this a cat or a dog? Is this email spam?).
    *   **Regression:** Predicting a continuous value (e.g., What will the price of this house be?).

### Unsupervised Learning: Learning on Your Own

**Unsupervised Learning** is like giving the child a big box of mixed fruit and asking them to sort it. You don't tell them what an "apple" or a "banana" is. You just say, "Find a way to group these."

The child will look at the fruit and start making their own piles based on patterns they observe:
*   "These are all red and round." (Apples)
*   "These are all yellow and long." (Bananas)
*   "These are small, round, and grow in bunches." (Grapes)

The child doesn't know the names "apple" or "banana," but they have successfully discovered the underlying structure in the data and separated the fruit into distinct groups.

**Core Idea:** The model learns from data that has **no labels**. It explores the data to find hidden patterns, structures, or clusters on its own.

**Key Characteristics:**
*   **Data:** Unlabeled data.
*   **Goal:** To discover the inherent structure or distribution of the data.
*   **Common Tasks:**
    *   **Clustering:** Grouping similar data points together (e.g., Segmenting customers into different purchasing groups).
    *   **Association:** Discovering rules that describe large portions of your data (e.g., "Customers who buy bread also tend to buy milk").

### How This Relates to LLMs

The development of a Large Language Model uses both of these learning types:

*   **Pre-training** is a form of **unsupervised learning** (specifically, "self-supervised" learning). The model is given a massive amount of raw text from the internet without explicit labels. Its task is simply to predict the next word in a sentence. The text itself provides the "answers," so no human needs to label it. This is how the model learns grammar, facts, and reasoning.
*   **Fine-Tuning** (specifically Supervised Fine-Tuning or SFT) is **supervised learning**. You provide the model with explicit "instruction" and "response" pairs (the labeled data) to teach it how to behave as a helpful assistant.
