# Results and interpretation

| Version | Overall | ROC-AUC | F1 |
| --- | ---: | ---: | ---: |
| V5 | 0.840764447 | 0.846591970 | 0.836879432 |
| V13 | 0.841324671 | 0.847992530 | 0.836879432 |
| V14 | 0.841436716 | 0.848272642 | 0.836879432 |
| **V15 (strongest in version history)** | **0.841567435** | **0.848599439** | **0.836879432** |
| V16 | 0.835233566 | 0.847899159 | 0.826789838 |

All are reported Zindi *public* evaluation scores, not an independent clinical validation.

Despite improving local grouped validation (mean +0.002955 over V15 in six runs), V16 declined **0.006333869** on Zindi. Its F1 was lower by approximately **0.01009**. V16 used substantially more positive class assignments than V15, indicating that the model's classification changes did not generalize in the same way as the local holdouts suggested.

The project owner reported a final position of **63rd among 1,601 participants**. This is a user-reported overall placement, not a claim that V16 was the best model.

The main lesson: robust local validation and preservation of the fixed threshold matter more than improving a repeatedly reused cross-validation score. Data shifts and changes around the 2017–2018 label patterns warrant further study.
