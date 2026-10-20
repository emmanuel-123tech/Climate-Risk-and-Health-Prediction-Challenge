# Model methodology

## Task and evaluation

Binary supervised classification: determine whether a mortality record is labelled as climate-sensitive. Zindi scores the required columns `TargetF1` (binary at the default 0.5 probability threshold) and `TargetRAUC` (uncut probability) with the metric `0.6 × F1 + 0.4 × ROC-AUC`.

## Data and feature engineering

The pipeline loads mortality and climate CSVs and creates age cohorts, calendar-year patterns, month/season encodings and interactions among age, location setting and time. Coordinates and IDs are excluded as direct predictors in the documented final model. The climate features were examined as candidate predictors; the final V16 signal depends primarily on demographic and temporal patterns.

## Model development

- **V5:** an ensemble using histogram gradient boosting with age/year/cohort features, plus a shallow boosting component.
- **V13–V15:** conservative regularized ranking-oriented additions to V5, improving public AUC while preserving F1.
- **V16:** a three-part probability blend: **40% V15, 40% smooth regularized age-by-time model, 20% richer age-interaction model**.

The latter two models use regularized nonlinear logistic transformations and are genuinely different from the tree-based components.

## Validation

The experiments used repeated location-grouped validation (six repeated geographic splits for the V16 final blend). Those splits reuse observations and reflect model-selection feedback, so they do not constitute six independent external test sets. A test-distribution reweighted variant was also considered.

V16 improved mean local validation but performed worse than V15 on the public leaderboard. This discrepancy is disclosed in the Results document.

## Limitations

This is a competition prediction task, not a causal attribution study. Temporal/age patterns may encode documentation changes, and the hidden test set differs from training geographically. The restricted public leaderboard may reward overfitting after many submissions.
