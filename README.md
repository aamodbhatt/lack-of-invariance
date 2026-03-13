## On the Lack of Answer Invariance in Large Language Models

# Repository Structure

```
answer-invariance-llms/
│
├── README.md
├── requirements.txt
├── LICENSE
│
├── paper/
│   └── paper.pdf
│
├── experiments/
│   ├── invariance_experiment.py
│   └── flip_experiment.py
│
├── data/
│   └── squad_subset.json
│
├── results/
│   ├── answer_invariance_results.csv
│   ├── answer_flip_results.csv
│   ├── answer_invariance_histogram.png
│   └── answer_flip_plot.png
│
└── scripts/
    └── run_experiments.sh
```

## Directory Description

**paper/**  
Contains the submitted research paper.

**experiments/**  
Core experiment scripts used to run the invariance and flip-rate evaluations.

**data/**  
Stores dataset subsets or processed inputs used for experiments.

**results/**  
Generated outputs from experiments including CSV results and figures.

**scripts/**  
Helper scripts for running experiments or reproducing results.

**requirements.txt**  
Lists Python dependencies needed to reproduce the experiments.

---

## Example `requirements.txt`

```
transformers
datasets
sentence-transformers
pandas
matplotlib
torch
tqdm
```

---

## Example `run_experiments.sh`

```
python experiments/invariance_experiment.py
python experiments/flip_experiment.py
```

---

This structure keeps the repository **simple, reproducible, and consistent with typical ML research projects.**
