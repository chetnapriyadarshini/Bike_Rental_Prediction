# Bike Rental Demand Prediction

A Jupyter Notebook applying multiple linear regression to forecast daily bike-sharing demand for BoomBikes, a US bike-rental provider, using two years of historical data to support post-pandemic revenue recovery planning.

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

BoomBikes suffered a significant revenue decline during the COVID-19 pandemic. As restrictions ease and the economy recovers, the company requires a data-driven understanding of which factors drive shared bike demand in the American market. This project builds an interpretable multiple linear regression model to identify the significant demand predictors and forecast daily rental counts, informing fleet management and targeted marketing strategy.

---

## Background

Bike-sharing demand is influenced by a combination of temporal, meteorological, and behavioural factors. Multiple linear regression provides an interpretable framework for quantifying the individual contribution of each predictor to demand, making it well-suited to generating business-actionable insights alongside predictions. This project follows a rigorous modelling workflow including assumption verification, multicollinearity checks (VIF), and residual diagnostics to ensure statistical validity of the final model.

---

## Dataset

| File | Description |
|---|---|
| `Bike_Rental.ipynb` | Main analysis notebook |
| `Linear Regression Subjective Questions.pdf` | Written analysis of regression assumptions, VIF interpretation, and business recommendations |

The dataset contains **732 daily observations** (2018–2019) with features including:

- **Temporal:** year, month, weekday, holiday, working day
- **Meteorological:** season, weather situation, temperature, apparent temperature, humidity, wind speed
- **Target variable:** `cnt` — total daily bike rentals (casual + registered users)

---

## Notebook Contents

| Section | Description |
|---|---|
| Data Loading & EDA | Distribution analysis, seasonal patterns, correlation heatmap, pairplots |
| Feature Engineering | Encoding categorical variables (season, weather, month), creating dummy variables |
| Train/Test Split | 70/30 stratified split for model training and evaluation |
| Model Building | Iterative feature selection using RFE (Recursive Feature Elimination) and p-value/VIF pruning |
| Assumption Verification | Linearity, normality of residuals, homoscedasticity, multicollinearity checks |
| Model Evaluation | R², Adjusted R², RMSE on train and test sets |
| Business Insights | Translating model coefficients into demand forecasting recommendations |

---

## Technologies Used

| Library | Version | Purpose |
|---|---|---|
| `pandas` | 2.0.3 | Data manipulation |
| `numpy` | 1.24.3 | Numerical operations |
| `scikit-learn` | 1.3.0 | Linear regression, RFE, train/test split |
| `matplotlib` | 3.7.2 | EDA and residual diagnostic plots |
| `python` | 3.11.5 | Runtime environment |

---

## Setup and Installation

```bash
git clone https://github.com/chetnapriyadarshini/Bike_Rental_Prediction.git
cd Bike_Rental_Prediction
pip install pandas numpy scikit-learn matplotlib
jupyter notebook Bike_Rental.ipynb
```

---

## Results and Conclusions

The final linear regression model explains a strong proportion of variance in daily bike rental demand. Key findings:

| Factor | Effect on Demand |
|---|---|
| **Year (2019 vs 2018)** | Positive — demand grew year-on-year, indicating market growth |
| **Temperature** | Strong positive — warmer weather drives significantly higher rentals |
| **September & October** | Peak rental months — likely due to optimal weather conditions |
| **Clear / partly cloudy weather** | Positive — ideal cycling conditions increase demand |
| **Snowfall / heavy rain** | Strong negative — adverse weather sharply reduces rentals |
| **Wind speed** | Negative — higher winds deter casual riders |
| **Humidity** | Negative — high humidity reduces rental activity |

**Business implication:** BoomBikes should maximise fleet availability and targeted promotions in September–October and during warm, clear weather periods. Winter and adverse weather months represent natural demand troughs where maintenance and repositioning activities can be scheduled.

---

## References

- Fanaee-T, H. & Gama, J. (2014). *Event labeling combining ensemble detectors and background knowledge*. Progress in Artificial Intelligence, 2, 113–127.

---

## Contact

Created by [@chetnapriyadarshini](https://github.com/chetnapriyadarshini) — feel free to reach out with questions or suggestions.
