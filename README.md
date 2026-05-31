# King County House Price Analysis

[![Python](https://img.shields.io/badge/Python-3.x-blue)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)](https://jupyter.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-brightgreen)](https://scikit-learn.org/)
[![IBM Course](https://img.shields.io/badge/IBM-Data%20Analysis%20with%20Python-052FAD)](https://www.coursera.org/learn/data-analysis-with-python)

> Predicting house sale prices in King County, USA using exploratory data analysis and machine learning regression models.

---

## 📋 Overview

This project analyzes **21,613 house sales** in King County (Seattle area) from May 2014 to May 2015. It walks through the full data science workflow — from data wrangling to model evaluation — and compares several regression approaches to predict sale price.

---

## Dataset

| Feature | Description |
|---|---|
| `price` | Sale price (prediction target) |
| `sqft_living` | Interior square footage |
| `grade` | King County grading score |
| `lat` / `long` | GPS coordinates |
| `waterfront` | Waterfront view flag |
| `yr_built` | Year built |
| ... | 21 features total |

Source: King County House Sales dataset (May 2014 – May 2015)

---

## Modules covered

**Module 1 — Data Import**
Load and inspect the dataset; review data types and summary statistics.

**Module 2 — Data Wrangling**
Drop irrelevant columns, handle missing values in `bedrooms` and `bathrooms` by imputing with column means.

**Module 3 — Exploratory Data Analysis**
- Floor distribution via `value_counts()`
- Boxplot: waterfront vs. non-waterfront price outliers
- Regplot: `sqft_above` vs. price (positive correlation = 0.61)
- Correlation matrix to identify the strongest price predictor (`sqft_living` = 0.70)

**Module 4 — Model Development**
| Model | R² |
|---|---|
| Linear Regression (`sqft_living` only) | 0.4929 |
| Linear Regression (11 features) | 0.6577 |
| Pipeline (Scaler + PolynomialFeatures + LR) | 0.7513 |

**Module 5 — Model Evaluation**
| Model | R² (test set) |
|---|---|
| Ridge Regression (α = 0.1) | 0.6480 |
| Poly(degree=2) + Ridge (α = 0.1) | 0.7004 |

---

## Getting started

```bash
git clone https://github.com/YOUR_USERNAME/king-county-house-price-analysis.git
cd king-county-house-price-analysis
pip install -r requirements.txt
jupyter notebook House_Sales_Solved.ipynb
```

---

## Tech stack

- Python 3.x
- pandas, NumPy
- Matplotlib, Seaborn
- scikit-learn (LinearRegression, Ridge, Pipeline, PolynomialFeatures)

---

## Key findings

- `sqft_living` is the single strongest predictor of price (r = 0.70).
- Waterfront properties have significantly higher prices and more outliers.
- A polynomial pipeline (degree 2) achieves the best R² of **0.75**.

---

## License

This project is based on the [IBM Data Analysis with Python](https://www.coursera.org/learn/data-analysis-with-python) course on Coursera. Dataset © IBM Corporation 2020.
