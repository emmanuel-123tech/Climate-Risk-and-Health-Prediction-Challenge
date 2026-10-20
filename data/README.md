# Challenge datasets

Source: [Zindi Climate Risk and Health Prediction Challenge](https://zindi.world/competitions/climate-risk-health-prediction-challenge). Zindi's competition-specific rules publish the data under CC BY-SA 4.0; credit Zindi and the organizers and share adaptations under the compatible terms.

The repo contains training and test CSVs, the supplementary climate variables and data dictionaries. The initial raw-column files and cleaned tables were reconstructed from the verified working data copy; expect harmless CSV-format or floating-point representation differences (typically around 1e-14) from the original download. For byte-exact copies, download directly from Zindi.

**3,146 training and 1,030 test rows**, and **4,176 supplementary climate-feature rows**. Target labels are present in training only. Do not interpret any individual record as demonstrating that climate caused a death; classification denotes climate-sensitive cause-of-death categories.

`data/raw/` has original-schema challenge inputs. `data/train_clean.csv` and `data/test_clean.csv` contain the post-merge model-ready tables. Use the documented notebook to reproduce cleaning and engineering. IDs are identifiers, not model predictors.

Health-related record-level data include location, age, and date. Please avoid attempts to re-identify individuals.
