# Reproducing the V16 experiment

## Requirements

- Python 3.11–3.13
- Dependencies in [requirements.txt](../requirements.txt)
- Input CSVs already included in [data/raw](../data/raw)
- A local Jupyter environment or Google Colab

## Recommended workflow

1. Clone or download this repository and install packages:

   ```bash
   git clone https://github.com/emmanuel-123tech/Climate-Risk-and-Health-Prediction-Challenge.git
   cd Climate-Risk-and-Health-Prediction-Challenge
   pip install -r requirements.txt
   jupyter notebook
   ```

2. Open [the author-uploaded V16 notebook](../_Climate_Risk_Health_Prediction_Ebiendele.ipynb).
3. Run the cells in order. It searches for the input files in `data/raw` when launched from the cloned repository. If running in an independent Colab environment, upload an archive with `data/raw` inside when prompted.
4. Read the Markdown interpretation immediately after each saved table or chart.
5. Training and submission cells generate `ID`, `TargetF1` and `TargetRAUC` in the notebook's output directory.

### Important distinctions

The public files were recovered from a previously enriched working copy. Training/test row order, labels, headers and feature semantics were preserved, but their low-order floating-point serialization might not be byte-for-byte the same as the original Zindi downloads. Use the official challenge downloads for exact source provenance.

Version and hardware differences can affect floating-point predictions. Earlier reproduction was checked against the archived V16 submission under its pinned run environment; reruns in newer libraries need their own validation.

The final score is determined by Zindi, not by the local cross-validation table. The model is not intended for individual mortality-risk decisions or medical diagnosis.
