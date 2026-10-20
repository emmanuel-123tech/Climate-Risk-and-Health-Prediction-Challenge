# Climate Risk & Health Prediction Challenge

**An end-to-end machine learning case study, from mortality data and climate features to a reproducible classification submission.**

This repository documents my work on the [Zindi Climate Risk and Health Prediction Challenge](https://zindi.world/competitions/climate-risk-health-prediction-challenge). The task is to predict whether a recorded death belongs to a climate-sensitive category using demographic, temporal, location, and climate information.

**Reported competition placement:** 63rd out of 1,601 participants. This is an overall placement I reported, not the score or placement of V16 alone.

## Results

| Submission | Public overall | ROC-AUC | F1 |
| --- | ---: | ---: | ---: |
| V5 | 0.840764447 | 0.846591970 | 0.836879432 |
| V13 | 0.841324671 | 0.847992530 | 0.836879432 |
| V14 | 0.841436716 | 0.848272642 | 0.836879432 |
| **V15 (best recorded here)** | **0.841567435** | **0.848599439** | **0.836879432** |
| V16 (documented experiment) | 0.835233566 | 0.847899159 | 0.826789838 |

The challenge weights **F1 60%** and **ROC-AUC 40%**. Binary predictions use the specified **0.5 threshold**. The leaderboard numbers are public evaluation results, not independent clinical validation.

## Notebooks

- [**V16: executed, annotated and interpreted notebook**](notebooks/Climate_Risk_Health_Prediction_V16_Interpreted.ipynb) — data understanding, exploratory analysis, cleaning, feature engineering, validation, modeling, submission, and interpretations placed under their outputs.
- [Original work-in-progress notebook](./_Climate_Risk_Health_Prediction_Ebiendele.ipynb) — preserved for history.

## Repository workflow

1. **Data understanding:** inspect columns, dimensions, missing values, and the classification target.
2. **EDA:** evaluate label distribution by age, year, demographics, and geography; compare train vs test.
3. **Cleaning:** normalize text and dates, join supplied climate features, audit outliers and coordinates; preserve rows and targets.
4. **Feature engineering:** age cohorts, year/time effects, cyclical seasons and interactions. Climate variables were evaluated but the strongest V16 components rely mainly on demographic and temporal signals.
5. **Model training:** V5 gradient-boosting baseline, V13–V15 improvements, then V16 smooth age/time and richer-age models.
6. **Validation:** grouped geographical holdouts, fixed-threshold F1, ROC-AUC and weighted score.
7. **Submission:** `ID`, `TargetF1`, and `TargetRAUC` columns.

## Reproduce in Colab

Open the interpreted notebook in [Google Colab](https://colab.research.google.com/). Run the setup cell and upload the ZIP archive containing the challenge CSVs when prompted. Alternatively use the datasets in the `data/` folder and adapt the notebook's data-root setup cell to your environment. Set a reproducible random seed and use the environment in [requirements.txt](requirements.txt).

The underlying cleaned tables contain **3,146 train rows** and **1,030 test rows**. The source datasets and dictionaries originate from Zindi and should be attributed accordingly.

## Lessons learned

The repeated location-grouped validation sometimes favored more aggressive age/time and climate models that subsequently underperformed on the public leaderboard. In particular V16 changed too many borderline binary classifications compared with V15. Model comparison requires checking both ranking quality and F1 generalization, not local validation alone.

**Interpretation:** The target indicates a *climate-sensitive mortality category*, not proof that climate directly caused a specific death. These predictions are research/competition outputs, not medical advice.

## Data license and attribution

Challenge data: [Zindi Climate Risk and Health Prediction Challenge](https://zindi.world/competitions/climate-risk-health-prediction-challenge). The challenge permits access, use and sharing under **[Creative Commons Attribution-ShareAlike 4.0](https://creativecommons.org/licenses/by-sa/4.0/)**. Credit Zindi and the challenge organizers when using these datasets, and comply with CC BY-SA 4.0 for adapted versions. Record-level entries include age, mortality date, and location; use care when redistributing or joining with other datasets.

Model implementation and documentation: this repository, by [emmanuel-123tech](https://github.com/emmanuel-123tech).
