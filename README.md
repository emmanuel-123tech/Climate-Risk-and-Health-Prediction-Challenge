# Climate Risk & Health Prediction Challenge

An end-to-end machine-learning project for the Zindi Climate Risk and Health Prediction Challenge, focused on predicting whether a mortality record is associated with a climate-sensitive outcome using structured health and climate features.

This repository captures the full workflow used in the project: exploratory analysis, data cleaning, feature engineering, model iteration, validation, and final reporting. It includes the original author-uploaded notebook, cleaned datasets, supporting documentation, and a snapshot of the performance history.

## Project objective

The task is a binary classification problem: determine whether a case should be labeled as climate-sensitive mortality based on a combination of demographic, time-based, geographic, and climate variables.

The official challenge evaluation prioritizes:

- F1 score: 60%
- ROC-AUC: 40%

The repository documents the modeling journey and the trade-offs between local validation and public leaderboard performance.

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
└── .gitignore
```

## What is in this repository

- `data/`: cleaned training/test data, raw challenge inputs, and dataset guidance
- `docs/`: project methodology, reproducibility notes, cleaning steps, and result interpretation
- `reports/`: recorded leaderboard outcomes and evaluation snapshots
- `_Climate_Risk_Health_Prediction_Ebiendele.ipynb`: the main notebook used for exploration, cleaning, modeling, and scoring
- `requirements.txt`: Python dependencies used to reproduce the environment

## Environment setup

Create and activate a virtual environment, then install dependencies:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

For Jupyter-based work:

```bash
jupyter notebook
```

Then open the notebook in the repository root or run the project in Google Colab using the notebook link below.

## Reproducing the workflow

The project is organized around a practical sequence:

1. Data inspection and target understanding
2. Exploratory data analysis
3. Data cleaning and schema harmonization
4. Feature engineering
5. Model training and iterative experimentation
6. Validation against grouped geographic splits
7. Public leaderboard scoring and interpretation

To reproduce the analysis:

- Open `_Climate_Risk_Health_Prediction_Ebiendele.ipynb`
- Run the setup cells
- Upload the challenge data archive when prompted, if required by the environment
- Follow the notebook pipeline through cleaning, feature engineering, model training, and output generation

## Results summary

The project records the following public leaderboard performance:

| Version | Overall | ROC-AUC | F1 |
| --- | ---: | ---: | ---: |
| V5 | 0.840764447 | 0.846591970 | 0.836879432 |
| V13 | 0.841324671 | 0.847992530 | 0.836879432 |
| V14 | 0.841436716 | 0.848272642 | 0.836879432 |
| V15 (best recorded here) | 0.841567435 | 0.848599439 | 0.836879432 |
| V16 (documented experiment) | 0.835233566 | 0.847899159 | 0.826789838 |

The repository also notes a reported final placement of 63rd out of 1,601 participants on Zindi, although this is a user-reported competition placement and not a claim that a single version was the best model at all times.

## Documentation index

- `docs/DATA_CLEANING.md` — cleaning logic and data preparation steps
- `docs/EXPLORATORY_ANALYSIS.md` — exploratory analysis and pattern discovery
- `docs/METHODOLOGY.md` — model methodology and validation design
- `docs/REPRODUCIBILITY.md` — setup and execution notes
- `docs/RESULTS.md` — experiment results and interpretation
- `data/README.md` — dataset guidance and licensing notes

## Data and attribution

This project uses data from the Zindi Climate Risk and Health Prediction Challenge:

- Challenge page: https://zindi.world/competitions/climate-risk-health-prediction-challenge

The repository includes the challenge data and the corresponding data license documentation under `data/`. The dataset is intended for research, analysis, and contest reproducibility. Please refer to the challenge terms and the included license files for exact usage conditions.

The modeling code and project documentation in this repository are authored by emmanuel-123tech and are provided as part of the project work.

## Notes and limitations

This project is a competition-focused prediction exercise, not a causal inference study. The target variable reflects a climate-sensitive mortality classification, and the repository explicitly warns against interpreting any single record as proof that climate caused a particular health outcome.

The challenge presents a geographic and temporal distribution shift, so robust validation and threshold-aware evaluation are essential. A model that performs well under repeated local validation may still underperform on the public leaderboard.

## License

Please check the included data and repository-level content for licensing terms before redistribution or commercial reuse. The repository itself is documented for research and reproducibility purposes, while the competition data retains its own licensing and attribution requirements.
