<div align="center">

### Exoplanet Classification

</div>

<div align="center">

[![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=fff)](#) [![Jupyter](https://img.shields.io/badge/Jupyter-ffffff?logo=Jupyter)](#) [![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=fff)](#) [![NumPy](https://img.shields.io/badge/NumPy-4DABCF?logo=numpy&logoColor=fff)](#) [![Scikit-learn](https://img.shields.io/badge/-scikit--learn-%23F7931E?logo=scikit-learn&logoColor=white)](#)

</div>

---

### Overview

A machine learning classifier that separates real exoplanets (`CONFIRMED`), unresolved signals (`CANDIDATE`) and non-planetary artifacts (`FALSE POSITIVE`) in the NASA Kepler Objects of Interest (KOI) cumulative table.

Columns that are outputs of NASA's own vetting pipeline are removed to avoid data leakage, and three transit-geometry features are engineered. Random Forest and XGBoost are compared with 5-fold stratified cross-validated macro-F1, using class weighting to handle the class imbalance, and the better model is scored on a held-out test set.

---

### Results

| Model | CV macro-F1 (5-fold) | Test accuracy | Test macro-F1 |
|---|---|---|---|
| Random Forest | 0.8153 ± 0.0091 | 0.8421 | 0.8144 |
| XGBoost | 0.8331 ± 0.0111 | 0.8594 | 0.8315 |

- XGBoost was selected as the best model.
- Test set: 1,913 objects (stratified 80/20 split of 9,564).
- XGBoost per-class F1: `FALSE POSITIVE` 0.91, `CONFIRMED` 0.90, `CANDIDATE` 0.69. `CANDIDATE` is the hardest class.

---

### Tech Stack

- **XGBoost** for gradient boosting
- **Matplotlib** and **Seaborn** for plots

---

### Installation

```bash
cd exoplanet-classification
pip install -r ../requirements.txt
```

---

### Usage

Place `KOI_Cumulative_clean.csv` (the NASA Kepler KOI cumulative table) in this folder, then open the notebook and run all cells from top to bottom:

```bash
jupyter notebook exoplanet_classification.ipynb
```

---

<div align="center">

Built by [Shaurya Chopra](https://shauryachopra.dev/)

</div>
