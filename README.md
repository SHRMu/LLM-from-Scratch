# LLM from Scratch: A Learner's Guide to Building After a Break

Welcome!

This book is for anyone who has taken a break from the rapidly evolving world of AI and wants to dive deep into Large Language Models (LLMs) from the ground up. Whether you're a student returning from a gap year, a professional re-entering the field, or simply someone looking for a structured path to understanding LLMs, you're in the right place.

Our journey will start with the fundamentals, assuming no prior knowledge of recent advancements. We'll build our understanding step-by-step, focusing on core concepts, practical implementation, and the intuition behind why these models work.

Let's begin this exciting journey together!

---

## Table of Contents

### Part 1: Core Concepts and Architectures

-   **Chapter 0: [Foundations - Math and AI](./chapters/00_foundations_math_and_ai/README.md)**
    -   [Essential Math for LLMs](./chapters/00_foundations_math_and_ai/01_essential_math.md)
    -   [Introduction to AI and Machine Learning](./chapters/00_foundations_math_and_ai/02_introduction_to_ai_and_ml.md)
    -   [Deep Learning Fundamentals](./chapters/00_foundations_math_and_ai/03_deep_learning_fundamentals.md)
-   **Chapter 1: [The Evolution of Sequence Models](./chapters/01_the_evolution_of_sequence_models/README.md)**
    -   [Recurrent Neural Networks (RNNs)](./chapters/01_the_evolution_of_sequence_models/01_recurrent_neural_networks.md)
    -   [Long Short-Term Memory (LSTMs) & GRUs](./chapters/01_the_evolution_of_sequence_models/02_long_short_term_memory.md)
    -   [Brief Interlude: Convolutional Neural Networks (CNNs) in NLP](./chapters/01_the_evolution_of_sequence_models/03_cnns_in_nlp.md)
    -   [The Bottleneck: Limitations of Sequential Processing](./chapters/01_the_evolution_of_sequence_models/04_limitations_of_sequential_processing.md)
    -   [Hands-on Guide: Building a Simple RNN](./chapters/01_the_evolution_of_sequence_models/05_hands_on_guide_rnn.md)
-   **Chapter 2: [The Transformer Architecture in Detail](./chapters/02_the_transformer_architecture_in_detail/README.md)**
    -   [Tokenization: The Vocabulary of Machines](./chapters/02_the_transformer_architecture_in_detail/01_tokenization.md)
    -   [Embeddings: Translating Tokens into Meaning](./chapters/02_the_transformer_architecture_in_detail/02_embeddings.md)
    -   [The Attention Mechanism: How Models Focus](./chapters/02_the_transformer_architecture_in_detail/03_attention.md)
    -   [Hands-on Guide: Calculating Attention](./chapters/02_the_transformer_architecture_in_detail/04_hands_on_guide_attention.md)

### Part 2: Applying and Specializing Models

-   **Chapter 3: [The Art of Fine-Tuning](./chapters/03_the_art_of_fine_tuning/README.md)**
    -   [What is Fine-Tuning?](./chapters/03_the_art_of_fine_tuning/01_what_is_fine_tuning.md)
    -   [Preparing Your Dataset](./chapters/03_the_art_of_fine_tuning/02_preparing_your_dataset.md)
    -   [Common Fine-Tuning Techniques](./chapters/03_the_art_of_fine_tuning/03_common_fine_tuning_techniques.md)
    -   [A Practical Example](./chapters/03_the_art_of_fine_tuning/04_a_practical_example.md)
-   **Chapter 4: [Retrieval-Augmented Generation (RAG)](./chapters/04_retrieval_augmented_generation/README.md)**
    -   [What is RAG?](./chapters/04_retrieval_augmented_generation/01_what_is_rag.md)
    -   [Building a Knowledge Base](./chapters/04_retrieval_augmented_generation/02_building_a_knowledge_base.md)
    -   [The Retrieval Process](./chapters/04_retrieval_augmented_generation/03_the_retrieval_process.md)
    -   [The Generation Process](./chapters/04_retrieval_augmented_generation/04_the_generation_process.md)
    -   [A Practical RAG Example](./chapters/04_retrieval_augmented_generation/05_a_practical_rag_example.md)
-   **Chapter 5: [From Generation to Action: LLM Agents and Tool Use](./chapters/05_from_generation_to_action/README.md)**
    -   [Introduction to Tool Use (Function Calling)](./chapters/05_from_generation_to_action/01_introduction_to_tool_use.md)
    -   [The Agentic Loop: How LLMs "Think"](./chapters/05_from_generation_to_action/02_the_agentic_loop.md)
    -   [Designing and Building an Agent](./chapters/05_from_generation_to_action/03_designing_and_building_an_agent.md)
    -   [A Practical Example: Building a Simple Agent](./chapters/05_from_generation_to_action/04_a_practical_example.md)

### Part 3: Advanced Topics & The Ecosystem

-   **Chapter 6: [Advanced Techniques: Reasoning and Efficient Inference](./chapters/06_advanced_techniques_reasoning_and_inference/README.md)**
    -   [Introduction to Reinforcement Learning](./chapters/06_advanced_techniques_reasoning_and_inference/00_introduction_to_reinforcement_learning.md)
    -   [Prompting for Reasoning: The Power of Chain-of-Thought](./chapters/06_advanced_techniques_reasoning_and_inference/01_prompting_for_reasoning.md)
    -   [Decoding Strategies: How LLMs Choose Their Words](./chapters/06_advanced_techniques_reasoning_and_inference/02_decoding_strategies.md)
    -   [Inference Optimization](./chapters/06_advanced_techniques_reasoning_and_inference/03_inference_optimization.md)
    -   [Hands-on Guide: Applying Decoding Strategies](./chapters/06_advanced_techniques_reasoning_and_inference/04_hands_on_guide_decoding.md)
-   **Chapter 7: [Evaluating LLMs and Ensuring Safety](./chapters/07_evaluating_llms_and_ensuring_safety/README.md)**
    -   [How to Evaluate LLMs](./chapters/07_evaluating_llms_and_ensuring_safety/01_how_to_evaluate_llms.md)
    -   [The Alignment Problem](./chapters/07_evaluating_llms_and_ensuring_safety/02_the_alignment_problem.md)
    -   [Bias, Fairness, and Misinformation](./chapters/07_evaluating_llms_and_ensuring_safety/03_bias_fairness_and_misinformation.md)
    -   [Red Teaming and Security](./chapters/07_evaluating_llms_and_ensuring_safety/04_red_teaming_and_security.md)
    -   [Hands-on Guide: Running an Evaluation Benchmark](./chapters/07_evaluating_llms_and_ensuring_safety/05_hands_on_guide_evaluation.md)
-   **Chapter 8: [The Open-Source Ecosystem and MLOps](./chapters/08_the_open_source_ecosystem_and_mlops/README.md)**
    -   [The Hugging Face Universe](./chapters/08_the_open_source_ecosystem_and_mlops/01_the_hugging_face_universe.md)
    -   [The Modern Stack: LangChain & LlamaIndex](./chapters/08_the_open_source_ecosystem_and_mlops/02_the_modern_stack.md)
    -   [Deploying LLMs: From Model to API](./chapters/08_the_open_source_ecosystem_and_mlops/03_deploying_llms.md)
    -   [Hands-on Guide: Building a Simple App with LangChain](./chapters/08_the_open_source_ecosystem_and_mlops/04_hands_on_guide_langchain.md)
-   **Chapter 9: [The Frontier: Multimodality and New Architectures](./chapters/09_the_frontier_multimodality_and_new_architectures/README.md)**
    -   [Introduction to Multimodality](./chapters/09_the_frontier_multimodality_and_new_architectures/01_introduction_to_multimodality.md)
    -   [Beyond the Transformer?](./chapters/09_the_frontier_multimodality_and_new_architectures/02_beyond_the_transformer.md)
    -   [Hands-on Guide: Using a Multimodal Model](./chapters/09_the_frontier_multimodality_and_new_architectures/03_hands_on_guide_multimodal.md)

### Part 4: Appendices

-   **Chapter 10: [Glossary](./chapters/10_glossary/README.md)**