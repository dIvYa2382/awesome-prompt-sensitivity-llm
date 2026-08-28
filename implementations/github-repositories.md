# GitHub Implementations

This section contains open-source implementations and frameworks relevant to prompt engineering, prompt optimization, reasoning, and systematic evaluation of Large Language Models.

---

## 1. Tree of Thoughts

**Repository:** Princeton NLP

**Description:**  
Official implementation of Tree of Thoughts, a reasoning framework that explores multiple reasoning paths instead of relying on a single chain of thought.

**Why it is relevant:**  
Different reasoning paths and prompting strategies can produce different outputs. This makes Tree of Thoughts useful for studying reasoning stability and prompt-dependent behaviour.

**GitHub:**  
https://github.com/princeton-nlp/tree-of-thought-llm

---

## 2. Large Language Models as Optimizers (OPRO)

**Repository:** Google DeepMind

**Description:**  
Official implementation of the paper "Large Language Models as Optimizers". OPRO uses language models to optimize instructions and solutions.

**Why it is relevant:**  
The project directly involves prompt/instruction optimization and can be used to investigate how changes in prompts influence model performance.

**GitHub:**  
https://github.com/google-deepmind/opro

---

## 3. LM Evaluation Harness

**Repository:** EleutherAI

**Description:**  
A unified framework for evaluating generative language models on a large number of standardized tasks and benchmarks.

**Why it is relevant:**  
It supports custom prompts and evaluation metrics, making it useful for controlled experiments comparing different prompt formulations.

**GitHub:**  
https://github.com/EleutherAI/lm-evaluation-harness

---

## 4. BIG-bench

**Repository:** Google Research

**Description:**  
BIG-bench is a collaborative benchmark containing a large collection of tasks designed to evaluate the capabilities and limitations of language models.

**Why it is relevant:**  
Its diverse tasks can be used to investigate whether prompt changes affect model behaviour consistently across different types of tasks.

**GitHub:**  
https://github.com/google/BIG-bench

**Note:** The repository was archived in April 2026 and is now read-only, but it remains an important benchmark implementation.

---

## 5. DSPy

**Repository:** Stanford NLP

**Description:**  
DSPy is a framework for programming and optimizing language-model systems. It provides algorithms for optimizing prompts and model weights.

**Why it is relevant:**  
DSPy is particularly relevant to prompt sensitivity because it provides systematic methods for optimizing instructions and demonstrations rather than relying only on manually written prompts.

**GitHub:**  
https://github.com/stanfordnlp/dspy

---

## 6. Promptfoo

**Repository:** Promptfoo

**Description:**  
Promptfoo is a framework and CLI for evaluating and testing LLM prompts and applications.

**Why it is relevant:**  
It allows different prompts and models to be compared systematically, making it useful for experiments involving prompt sensitivity and output stability.

**GitHub:**  
https://github.com/promptfoo/promptfoo
