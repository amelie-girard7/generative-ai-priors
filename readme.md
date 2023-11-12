# Bayesian Networks and Large Language Models for Causal Inference

## Table of Contents
1. [Research Questions](#research-questions)
2. [Background](#background)
3. [Methodology](#methodology)
    - [Step 1: Generate Sample Set](#Step1-Generate-Samples)
    - [Step 2: Convert Sample Set to Human-Readable Language and Use as Context](#step2-convert-sample-to-human-language)
4. [Results](#results)
5. [How to Run The Notebooks](#How_to_Run_Notebooks)
6. [References](#references)
7. [Contact](#contact)

---

## Research Questions
- **Question 1:** Can Large Language Models (LLMs) provide useful prior knowledge to guide causal discovery and structure learning?
- **Question 2:** Context versus Training data: Which approach provides more information for causal discovery and structure learning?

---

## Background

### Causal Discovery
Refers to the process or algorithms used to identify and infer the underlying causal relationships among a set of variables. It involves analyzing data (either observational or experimental) to deduce the causal connections between variables, aiming to go beyond mere statistical correlation.

### Causal Structure
Refers to the underlying pattern or model that represents the causal relationships among the variables. Causal structures are often represented using directed acyclic graphs (DAGs).

---
## Methodology

### Step 1: Generate Sample Set

Suppose we have a ground truth distribution,\(p(G, θG)), over graphs, \( G \), and graph parameters, θG that jointly define BN structures over a joint distribution \( p(X_{1:d}) \) of some Random variables \( X_{1:d} \). (Note: in the simplest case, the graph distribution can be a Dirac delta on a single ground-truth graph).

Given the ground truth distribution \(p(G, θG)), we can generate \( N \) realizations of \( d \) binary random variables. Let's assume \( d = 3 \) and the variables are \( I \), \( D \), and \( G \) representing intelligence, exam difficulty, and grade, respectively.


### Step 2: Convert Sample Set to Human-Readable Language and Use as Context
We'll convert these samples to human-understandable language and use them as a context in a conversation with an LLM.
Example: let we have \( d = 3 \) binary random variables \( I \), \( D \), and \( G \) that denote intelligence, (exam's) difficulty, and grade, respectively. Let a sample be \( (I = 1, D = 0, G = 0) \).

- We use an LLM to make a story out of these clunky forms. For instance, "Despite the fact that Alice is known to be quite intelligent and the Math exam was not that hard, unfortunately her performance was not satisfactory..."
- We feed this story as the context material to another LLM. (or as training data for fine-tuning to answer Question 2)
     . 



### Generate the stories using GPT4 and store the stories in a CSV file

We use an LLM to make a story out of these samples. For
instance “Despite the fact that Alice is known to be quite intelligent
and the Math exam was not that hard, unfortunately her performance
we not satisfactory...”

---

## Results
- To be updated

## References
- [Generative AI and LLMs as Prior Knowledge](https://www.overleaf.com/project/64d3099c8beb74285fc06d34)
- [Paper2](#)

## Contact
Name: Amelie Girard
Email: amelie.girard@student.uts.edu.au
LinkedIn: https://www.linkedin.com/in/ameliegds/


## How to Run Notebooks

1. **Bayesian Networks:** Define the Bayesian Network model, including the structure and Conditional Probability Distributions (CPDs).
2. **Sample Generation:** Generate samples from the Bayesian Network. 
3. **Context Conversion:** Convert these samples into human-readable language
4. **Story Generation:** Feed these contexts into an LLM to generate narrative stories.

To run the Jupyter Notebooks in sequence, open the main notebook and execute the following cells:

```python
%run ./src/Bayesian_Networks.ipynb
%run ./src/Sample_Generation.ipynb
%run ./src/Context_Conversion.ipynb
%run ./src/Story_Generation.ipynb
%run ./src/Causal_Inference.ipynb
