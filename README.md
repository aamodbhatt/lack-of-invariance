# On the Lack of Answer Invariance in Large Language Models



This repository contains the code and experimental results for the paper:

**"On the Lack of Answer Invariance in Large Language Models"**  
*Aamod Bhatt – Independent Researcher*

## Overview

Large Language Models (LLMs) are expected to produce consistent answers for semantically equivalent questions. However, minor paraphrasing of a question may lead to different responses.

This project investigates **answer invariance under semantic paraphrasing** by measuring how stable LLM outputs are when questions are rephrased.

We introduce the **Answer Invariance Score**, which measures semantic similarity between answers generated for the original question and its paraphrased versions.

---

## Experiments

Two main experiments were conducted:

### 1. Answer Invariance Score

For each question:

1. Generate two paraphrases of the original question
2. Query the model with all three versions
3. Compute semantic similarity between answers using sentence embeddings

**Metric**

```
Answer Invariance Score = average cosine similarity between answers
```

Observed mean score:

```
0.6968
```

This indicates substantial variability in answers across semantically equivalent queries.

---

### 2. Answer Flip Rate

We also measure **literal answer consistency**.

If the answers to paraphrased questions differ textually from the original answer, the instance is counted as a **flip**.

Results show that **literal answer invariance is rare**, indicating strong sensitivity to question phrasing.

---

## Model and Dataset

**Language Model**

- Mistral-7B-Instruct

**Dataset**

- SQuAD Question Answering Dataset

**Embedding Model**

- all-MiniLM-L6-v2

---

## Repository Structure

```
.
├── experiments/
│   ├── invariance_experiment.py
│   └── flip_experiment.py
│
├── results/
│   ├── answer_invariance_results.csv
│   ├── answer_flip_results.csv
│   ├── answer_invariance_histogram.png
│   └── answer_flip_plot.png
│
├── paper/
│   └── paper.pdf
│
└── README.md
```

---

## Running the Experiment

Install dependencies:

```
pip install transformers datasets sentence-transformers pandas matplotlib torch
```

Run the invariance experiment:

```
python invariance_experiment.py
```

Run the flip experiment:

```
python flip_experiment.py
```

---

## Key Findings

- LLM answers vary significantly under paraphrasing.
- Average semantic similarity between answers is **0.6968**.
- Exact textual invariance is extremely rare.
- This suggests **LLM responses are sensitive to input phrasing**, which may affect evaluation reliability.

---

## Citation

If you use this work, please cite:

```
Bhatt, A. (2026).
On the Lack of Answer Invariance in Large Language Models.
```

---

## License

MIT License
