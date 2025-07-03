# Introduction: How LLMs Work & How to Steal Them
# IMPORTANT: Plesae make sure to create a hugging face access token to be able to run the demo 


## 1. How LLMs Work

Large Language Models (LLMs) like GPT-2, GPT-3, and Mistral are deep neural networks trained to generate and understand human language.

Input: A text prompt (e.g., "The capital of France is")
Output: The most likely next word(s) (e.g., "Paris")
LLMs can answer questions, write stories, translate languages, and more just by generating text one token at a time.

## 2. How LLM Training Works

LLMs are trained on massive datasets of text (books, websites, articles) using self-supervised learning:
The model sees lots of text and tries to predict the next word in each sentence.
It learns patterns, facts, grammar, and even some reasoning just from data.
Training requires huge amounts of data, compute, and time.

Result:
A model that can generate realistic, context-aware text for almost any prompt.

## 3. How to Steal a Model Using Its Responses
Even if you don't have access to the original model's code or weights, you can "steal" (clone) it using a process called model extraction or Adversary nets:

### Query the Victim Model:
Send it lots of prompts (questions, instructions, etc.).
Collect its responses (outputs).

### How to Prompt for Extraction
Diversity: Use prompts that cover many topics (e.g., science, history, jokes, instructions) and formats (questions, stories, explanations).
Templates: Create prompt templates with placeholders (e.g., "What is the capital of {}?") and fill them with different subjects to generate a large pool of unique prompts.
Randomization: Shuffle and select prompts randomly to avoid bias and ensure broad coverage.
Pairing: For each prompt, record the model's output. Each (prompt, output) pair becomes a training example for your clone.

### Build a Dataset:
Each (prompt, output) pair becomes a training example.

### Train an Adversary Model:
Use the collected data to train your own model to mimic the victim’s behavior.
The more data you collect, the better your Adversary can imitate the original.

### Why is this important?
It shows that even black-box models (API-only, no code access) can be cloned if you can query them.
This has implications for AI security, intellectual property, and responsible deployment.

### In this demo, you’ll see each step:

- Generating prompts
- Querying a victim LLM
- Building a dataset
- Training a adversary model
- Comparing the adversary's outputs to the original


