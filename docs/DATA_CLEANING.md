# Data cleaning and integrity checks

Cleaning was reconstructed from the original project script, not reverse engineered from target labels. The documented notebook runs it from raw files.

1. Read original train (3,146) and test (1,030), plus 4,176 supplemental climate rows.
2. Normalize identifier, gender, zone and location text (Unicode NFKC, collapsed spaces). Parse dates with YYYY-MM-DD.
3. Confirm unique IDs, non-overlapping train/test IDs, plausible age and geographic coordinates, and a binary training target.
4. Reconcile one confirmed alternative location spelling, without moving geographic coordinates.
5. Add descriptive audit flags for age-zero, age multiples of five, repeated-location coordinate disagreement, distant coordinates and duplicate predictors.
6. Merge the climate table one-to-one by ID and death date. Check complete merges, plausible temporal rainfall sums, NDVI and temperature ordering.
7. Remove the constant `hot_days_30d` column from model-ready exports.
8. Preserve every mortality record, age value, target label, and original geographic coordinate.

The flags are for quality assessment; they should not be mistaken for causal explanations. The model validation groups locations to reduce geographic leakage.

**Reproducibility note:** public CSVs were restored from our verified enriched copy, so formatting and a handful of low-order floating-point decimals may differ from the exact original download. For original-byte fidelity use the organizer's official data export. The executable notebook is the source of truth for the cleaning workflow.
