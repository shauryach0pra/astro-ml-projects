<div align="center">

### Mars Humidity Regression

</div>

<div align="center">

[![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=fff)](#) [![Jupyter](https://img.shields.io/badge/Jupyter-ffffff?logo=Jupyter)](#) [![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=fff)](#) [![NumPy](https://img.shields.io/badge/NumPy-4DABCF?logo=numpy&logoColor=fff)](#) [![Scikit-learn](https://img.shields.io/badge/-scikit--learn-%23F7931E?logo=scikit-learn&logoColor=white)](#)

</div>

---

### Overview

Predicts a Mars rover's humidity reading (`HUMIDITY_Sensor_A`) from its other sensors using Linear Regression, Ridge (L2) and Lasso (L1).

Missing values, `-999` placeholders and sensor spikes are cleaned out. The inputs include time of day (sin and cos), temperature squared and cubed, and the differences between the three temperature sensors. Humidity is skewed, so the models predict log(1 + humidity). The train/test split is by sol (Martian day) rather than by random rows, because readings one second apart are almost identical.

---

### Results

| Model | Test R² | Test MSE |
|---|---|---|
| Linear Regression | 0.871 | 0.953 |
| Ridge (L2) | 0.871 | 0.953 |
| Lasso (L1) | 0.874 | 0.934 |

- Tested on 5 sols the models never saw (405, 410, 416, 421, 426): 18,993 test rows and 85,287 training rows.
- The three models score almost the same, so Ridge and Lasso add little on this data.
- The new features matter (Linear Regression R²): raw sensors 0.686, with the log target 0.792, with all new features 0.871.
- Temperature is the main input. Removing it drops R² from 0.871 to 0.685.
- Repeating the sol split 10 times with random held-out sols gives a mean R² of 0.819 (std 0.091, range 0.639 to 0.957), so about 0.82 is a fairer expectation than 0.874.
- Sol 416 is a short partial sol (about 800 rows) with a negative R² of -1.08.

---

### Usage

Open `mars_humidity_regression.ipynb` in Google Colab and run all cells from top to bottom. The first data cell asks you to upload the rover sensor CSV (about 1 million rows, one reading per second). The notebook keeps every 10th row so it runs faster.

---

<div align="center">

Built by [Shaurya Chopra](https://shauryachopra.dev/)

</div>
