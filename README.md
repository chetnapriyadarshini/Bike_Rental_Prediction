# Property Price Prediction

A Jupyter Notebook building a regularised regression model to predict residential property sale prices in the Australian market, helping a US-based investment company — Surprise Housing — identify undervalued properties for strategic acquisition.

---

## Table of Contents

- [Overview](#overview)
- [Background](#background)
- [Dataset](#dataset)
- [Notebook Contents](#notebook-contents)
- [Technologies Used](#technologies-used)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
- [Results and Conclusions](#results-and-conclusions)
- [References](#references)
- [Contact](#contact)

---

## Overview

Surprise Housing, a US-based property investment firm, is entering the Australian real estate market. Their strategy involves purchasing properties below market value and selling them at a profit. This project builds a predictive regression model — incorporating Lasso and Ridge regularisation — to estimate the actual market value of prospective properties, providing a data-driven basis for investment decisions.

---

## Background

Predicting property prices is a regression problem with high-dimensional feature spaces, multicollinearity between predictors, and a mix of categorical and continuous variables. Standard linear regression is prone to overfitting in such settings. Regularisation techniques — Ridge (L2) and Lasso (L1) — penalise model complexity to improve generalisation. Lasso additionally performs implicit feature selection by shrinking less informative coefficients to zero, making it particularly interpretable for identifying the true drivers of property value.

---

## Dataset

| File | Description |
|---|---|
| `train.csv` | Training data with 80+ property features and sale prices (Australian market) |
| `SubjectiveQuestions.pdf` | Written analysis of model choices, regularisation interpretation, and business insights |

Key features include structural attributes (floor area, year built), quality ratings (kitchen quality, overall condition), location (neighbourhood), and sale conditions.

---

## Notebook Contents

| Section | Description |
|---|---|
| Data Loading & EDA | Loading data, distribution analysis, missing value treatment, outlier inspection |
| Feature Engineering | Encoding categorical variables, handling skewed distributions, creating derived features |
| Train/Validation Split | Splitting data for unbiased hyperparameter tuning |
| Linear Regression Baseline | Establishing an unregularised benchmark |
| Ridge Regression | L2 regularisation with cross-validated alpha selection |
| Lasso Regression | L1 regularisation with feature selection and alpha tuning |
| Model Evaluation | RMSE, R², residual analysis on validation and test sets |
| Feature Importance | Identifying the 12 most influential predictors of sale price |
| Business Insights | Translating model coefficients into actionable investment guidance |

---

## Technologies Used

| Library | Version | Purpose |
|---|---|---|
| `pandas` | 2.0.3 | Data manipulation |
| `numpy` | 1.24.3 | Numerical operations |
| `scikit-learn` | 1.3.0 | Regression models, regularisation, cross-validation |
| `matplotlib` | 3.7.2 | EDA and residual plots |
| `python` | 3.11.5 | Runtime environment |

---

## Setup and Installation

```bash
git clone https://github.com/chetnapriyadarshini/PropertyPricePrediction.git
cd PropertyPricePrediction
pip install pandas numpy scikit-learn matplotlib
jupyter notebook "Property Pricing.ipynb"
```

---

## Results and Conclusions

The Lasso model identifies **12 variables** as the primary predictors of property price. Key findings:

| Predictor | Direction | Interpretation |
|---|---|---|
| `YearBuilt` | Positive | Newer properties command higher prices |
| `1stFlrSF` | Positive | Larger ground floor area increases value |
| `2ndFlrSF` | Positive | Multi-storey properties are valued higher |
| `KitchenQual_TA` (Typical) | **Negative** | Below-average kitchen quality suppresses price |
| `Crawford` neighbourhood | Positive | Crawford is the highest-value neighbourhood in the dataset |

**Investment implication:** Properties in Crawford with large floor areas and recent construction year represent the highest-value acquisition targets for Surprise Housing's Australian strategy.

---

## Contact

Created by [@chetnapriyadarshini](https://github.com/chetnapriyadarshini) — feel free to reach out with questions or suggestions.
