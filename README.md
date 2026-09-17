# Towards Enhanced Breast Cancer Prediction: A Comparative Evaluation Study

Published research + an independent, executable reproduction of its machine learning pipeline.

**Ahmed Zafran Bin Ahmed Sharizan**, Mohsen Marjani, Dalia Abdulkareem Shafiq, NZ Jhanjhi,
David A/L Asirvatham, Komal Sharma. *2024 International Conference on Emerging Trends in
Networks and Computer Communications (ETNCC)*, IEEE, 2024.

DOI: [10.1109/ETNCC63262.2024.10767547](https://doi.org/10.1109/ETNCC63262.2024.10767547)

## Abstract

Breast cancer remains a foremost cause of mortality among women globally. This study presents a
comparative evaluation of supervised machine learning classification algorithms — **K-Nearest
Neighbors (KNN)**, **Logistic Regression (LR)**, and **Random Forest (RF)** — for distinguishing
malignant from benign tumors on the Breast Cancer Wisconsin (Diagnostic) dataset. Using LASSO
feature selection, Min-Max scaling, and hyperparameter tuning, the Random Forest model achieved
the highest accuracy (97.08%), followed by KNN (95.91%) and Logistic Regression (94.15%),
alongside AUC scores of 0.95, 0.91, and 0.94 respectively.

## What's in this repository

| Path | Contents |
|---|---|
| [`notebook/breast_cancer_prediction.ipynb`](notebook/breast_cancer_prediction.ipynb) | An independent, executed reproduction of the paper's six-phase pipeline (preprocessing, LASSO feature selection, Min-Max scaling, model selection, hyperparameter tuning via cross-validation, evaluation), with all figures regenerated from real runs |
| `requirements.txt` | Exact packages needed to re-run the notebook |
| `paper/` | Full-text PDF of the published paper *(added separately — see below)* |

## About the reproduction

The notebook re-implements the paper's methodology from its written description rather than
running unpublished original source code, so a handful of details the paper doesn't fully pin
down (the exact LASSO alpha, the outlier-removal row-drop threshold, single-split vs.
cross-validated hyperparameter tuning) were filled in with standard, clearly documented choices.
Results land in the same range as the paper — all three models score in the low-to-high 90s with
strong AUC — though the exact ranking and numbers differ slightly run to run, for reasons the
notebook's own Discussion section walks through. It also acts on two limitations the paper's own
"Future Work" section names directly: hyperparameter tuning here is cross-validated rather than
checked once against the test set, and a training-set-proportion sensitivity sweep (paper Fig. 8)
is included as part of that same tuning discussion rather than only as a post-hoc plot.

Dataset: same underlying UCI source the paper cites (Wolberg et al., 1995, *Breast Cancer
Wisconsin (Diagnostic)*), loaded via scikit-learn's bundled copy — no external download needed.

## Running it yourself

```bash
python -m venv venv
source venv/bin/activate   # venv\Scripts\activate on Windows
pip install -r requirements.txt
jupyter notebook notebook/breast_cancer_prediction.ipynb
```

## Citation

```bibtex
@inproceedings{sharizan2024breastcancer,
  title     = {Towards Enhanced Breast Cancer Prediction: A Comparative Evaluation Study},
  author    = {Sharizan, Ahmed Zafran Bin Ahmed and Marjani, Mohsen and Shafiq, Dalia Abdulkareem
               and Jhanjhi, NZ and Asirvatham, David A/L and Sharma, Komal},
  booktitle = {2024 International Conference on Emerging Trends in Networks and Computer
               Communications (ETNCC)},
  year      = {2024},
  publisher = {IEEE},
  doi       = {10.1109/ETNCC63262.2024.10767547}
}
```
