# Exploratory data analysis

The documented [notebook](../notebooks/Climate_Risk_Health_Prediction_V16_Interpreted.ipynb) includes executed charts and interpretation immediately beneath the output.

- Training: **3,146 rows**, test: **1,030 rows**, historical dates **2007–2022**.
- Overall training positive-label rate: **65.07%**. This is the share of deaths labelled as belonging to a climate-sensitive category, not the share proven caused by climate.
- Training setting composition: approximately **62.68% rural**, **37.32% peri-urban**. Test: approximately **76.21% rural**, **23.79% peri-urban**. Distribution shift is important when assessing generalization.
- Younger age cohorts show substantially higher positive-label rates, while older adults are difficult to classify. Zero-age records change markedly after about 2017–2018.
- That age-zero transition may reflect classification, sampling or recording changes. The available data cannot prove the cause of the break.
- Supplemental climate features provide rainfall, temperature, NDVI and terrain; adding these wholesale did not improve the strongest model in the controlled local experiments.
- All train/test records are retained; no target labels are altered during cleaning.

Charts and outputs are embedded in the executed notebook. Their associations should not be interpreted as individual-level climate causality.
