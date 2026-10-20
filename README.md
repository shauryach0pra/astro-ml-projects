<div align="center">

### Astro ML Projects

</div>

<div align="center">

[![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=fff)](#) [![Jupyter](https://img.shields.io/badge/Jupyter-ffffff?logo=Jupyter)](#) [![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=fff)](#) [![NumPy](https://img.shields.io/badge/NumPy-4DABCF?logo=numpy&logoColor=fff)](#) [![Scikit-learn](https://img.shields.io/badge/-scikit--learn-%23F7931E?logo=scikit-learn&logoColor=white)](#)

</div>

---

### Overview

A collection of machine learning notebooks on astronomy data.

- **Exoplanet Classification** sorts NASA Kepler signals into confirmed planets, unresolved candidates and false positives.
- **Mars Humidity Regression** predicts a Mars rover's humidity reading from its other sensors.

---

### Projects

| Project | Task | Models | Headline result |
|---|---|---|---|
| [Exoplanet Classification](exoplanet-classification/) | Classification (3 classes) | Random Forest, XGBoost | XGBoost: 0.8594 test accuracy, 0.8315 macro-F1 |
| [Mars Humidity Regression](mars-humidity-regression/) | Regression | Linear, Ridge (L2), Lasso (L1) | Lasso: 0.874 test R² (about 0.82 across 10 random sol splits) |

---

### Project Structure

```
astro-ml-projects/
├── README.md
├── requirements.txt                       # shared dependencies
├── .gitignore
├── exoplanet-classification/
│   ├── README.md
│   └── exoplanet_classification.ipynb     # Random Forest vs XGBoost on Kepler KOI data
└── mars-humidity-regression/
    ├── README.md
    └── mars_humidity_regression.ipynb     # Linear, Ridge and Lasso on rover sensor data
```

---

### Tech Stack

- **XGBoost** for gradient boosting
- **Matplotlib** and **Seaborn** for plots

---

### Datasets

Datasets are not included in this repo.

- `exoplanet-classification` expects `KOI_Cumulative_clean.csv` (the NASA Kepler KOI cumulative table) in its folder.
- `mars-humidity-regression` asks you to upload the rover sensor CSV when the notebook runs.

---

### Installation

```bash
pip install -r requirements.txt
```

This covers the exoplanet notebook. The Mars notebook runs in Google Colab.

---

### Usage

Each project folder has its own README with the exact run steps:

- [Exoplanet Classification](exoplanet-classification/README.md): add the CSV next to the notebook and open it in Jupyter.
- [Mars Humidity Regression](mars-humidity-regression/README.md): open the notebook in Google Colab and upload the CSV when asked.

---

<div align="center">

Built by [Shaurya Chopra](https://shauryachopra.dev/)

</div>