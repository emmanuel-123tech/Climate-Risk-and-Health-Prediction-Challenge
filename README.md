# Climate Risk & Health Prediction Challenge

A reproducible machine-learning project for the Zindi Climate Risk and Health Prediction Challenge, focused on predicting climate-sensitive mortality outcomes from structured health and environmental data.

This repository documents the end-to-end workflow used in the project: exploratory analysis, data preparation, feature engineering, model iteration, grouped validation, and leaderboard evaluation. It includes the original author-uploaded notebook, cleaned datasets, supporting documentation, and a summary of the experimental results.

## Project objective

The challenge is a binary classification task: determine whether a mortality record belongs to a climate-sensitive outcome category based on demographic, geographic, time-based, and climate-related variables.

The task is scored using the competition weighting:

- F1 score: 60%
- ROC-AUC: 40%

The project emphasizes both predictive performance and the practical importance of threshold-aware evaluation under real-world data shifts.

## Repository structure

```text
.
├── README.md
├── requirements.txt
├── _Climate_Risk_Health_Prediction_Ebiendele.ipynb
├── data/
│   ├── README.md
│   ├── LICENSE-CC-BY-SA-4.0.md
│   ├── raw/
│   ├── train_clean.csv
│   ├── test_clean.csv
│   ├── sample_submission.csv
│   └── ...
├── docs/
│   ├── DATA_CLEANING.md
│   ├── EXPLORATORY_ANALYSIS.md
│   ├── METHODOLOGY.md
│   ├── REPRODUCIBILITY.md
│   ├── RESULTS.md
│   └── ...
├── reports/
│   └── leaderboard_scores.csv
├── .gitignore
└── ...
```

## What is included

- `data/`: challenge datasets, cleaned tables, and dataset documentation
- `docs/`: methodological notes, reproducibility details, exploratory analysis, and result interpretation
- `reports/`: leaderboard score summaries and experiment records
- `_Climate_Risk_Health_Prediction_Ebiendele.ipynb`: main notebook with the project workflow and model development
- `requirements.txt`: Python dependencies required to reproduce the environment

## Environment setup

Create a virtual environment and install the dependencies:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

For notebook-based work:

```bash
jupyter notebook
```

The notebook is designed to be run in a local environment or opened in Google Colab, where the challenge CSV archive can be uploaded when required.

## Reproducibility workflow

The project follows a standard machine-learning research pipeline:

1. Data inspection and schema review
2. Exploratory analysis of class balance and feature distributions
3. Cleaning and schema harmonization
4. Feature engineering across age, time, geography, and climate dimensions
5. Model training and iteration across multiple versions
6. Validation with grouped geographic splits
7. Public metric comparison and result interpretation

The notebook captures the experimental history from baseline models through iterative model refinements.

## Results summary

The repository records the following public leaderboard scores from the challenge:

| Version | Overall | ROC-AUC | F1 |
| --- | ---: | ---: | ---: |
| V5 | 0.840764447 | 0.846591970 | 0.836879432 |
| V13 | 0.841324671 | 0.847992530 | 0.836879432 |
| V14 | 0.841436716 | 0.848272642 | 0.836879432 |
| V15 (best recorded here) | 0.841567435 | 0.848599439 | 0.836879432 |
| V16 (documented experiment) | 0.835233566 | 0.847899159 | 0.826789838 |

The project documentation also notes a reported final competition placement of 63rd out of 1,601 participants. This is a user-reported overall placement and is not presented as evidence that a single model version was definitively optimal across all evaluation settings.

## Documentation index

- `docs/DATA_CLEANING.md` — data preparation and schema cleaning steps
- `docs/EXPLORATORY_ANALYSIS.md` — exploratory analysis and feature diagnostics
- `docs/METHODOLOGY.md` — model design, validation approach, and feature-engineering rationale
- `docs/REPRODUCIBILITY.md` — environment and execution guidance
- `docs/RESULTS.md` — experiment outcomes and interpretation
- `data/README.md` — data summary, attribution, and challenge-specific guidance

## Data and attribution

This repository uses data from the Zindi Climate Risk and Health Prediction Challenge:

- https://zindi.world/competitions/climate-risk-health-prediction-challenge

The dataset and supporting documentation are included in the repository under `data/`, along with licensing and attribution information for challenge content. The project documentation also clarifies that the target variable identifies a climate-sensitive mortality category rather than proving a direct causal effect of climate on any single record.

## Key methodological notes

This project is a predictive modeling exercise rather than a causal inference study. The repository explicitly emphasizes that the target should not be interpreted as proof that climate directly caused a specific death.

A central finding in the project is that local grouped validation can be optimistic relative to public leaderboard performance. This is especially relevant in competition settings with geographic and temporal distribution shift, where threshold-sensitive metrics such as F1 can behave differently from AUC-like metrics.

## License and usage

Please review the included challenge data license and documentation before redistributing or reusing the data beyond the scope of the project. The repository is intended for research, reproducibility, and educational review, with challenge-specific licensing requirements retained for the underlying dataset.

## Summary

This repository presents a structured and reproducible approach to a climate-health prediction challenge, combining realistic feature engineering, iterative experimentation, and careful interpretation of model performance under competition conditions.
