
# Farmer Income Prediction using Data-Driven Feature Engineering

## Overview
This project builds a machine learning pipeline to estimate the annual income of farmers using demographic, agricultural, environmental, and economic features. The approach emphasizes domain-driven feature engineering and robust evaluation.

Presentation: Team-1.pdf

---

## Problem Statement
A significant portion of farmers lack formal credit histories, making it difficult for financial institutions to assess their economic potential. The objective of this project is to develop a predictive model that estimates farmer income accurately, thereby supporting credit access, risk assessment, and financial inclusion.

---

## Dataset
The dataset captures multiple aspects of agricultural life:

- Demographics: age, education level, geographic region  
- Agricultural features: farm size, cropping density, irrigation, soil type  
- Environmental factors: rainfall, temperature, agro-climatic zones  
- Economic indicators: market access, commodity prices, infrastructure  

---

## Exploratory Data Analysis

Key findings from the analysis include:

- The target variable shows strong right skewness with high-income outliers  
- Log transformation was applied to stabilize variance  
- Non-agricultural income shows strong positive correlation with total income  
- Agricultural productivity indicators are strong predictors  
- Farm size and market accessibility have moderate influence  

---

## Feature Engineering

- Temporal aggregation of climate variables using multi-year averages  
- Extraction of features from agro-ecological zone information  
- Creation of agricultural productivity indicators  
- Market accessibility feature combining distance-based metrics  
- Removal of redundant and low-signal features  

A correlation-weighted socio-economic index was tested but discarded due to reduced model performance.

---

## Model and Methodology

Model used: XGBoost Regressor

Pipeline:
1. Data cleaning  
2. Log transformation  
3. Outlier clipping (98th percentile)  
4. Feature engineering  
5. Encoding  
6. Model training  
7. 5-fold cross validation  

---

## Evaluation Metrics

- Mean Absolute Percentage Error (MAPE)  
- Mean Absolute Error (MAE)  
- Root Mean Squared Error (RMSE)  
- R-squared  

Custom metric:
- Poverty Misclassification Risk (PMR)

---

## Results

| Metric | Value |
|--------|--------|
| MAPE | 19.96 |
| MAE | 214360 |
| RMSE | 347412 |
| R² | 0.604 |
| PMR | 8.47% |

---

## Key Insights

- Agricultural productivity is a primary driver of income  
- Non-agricultural income significantly impacts total income  
- Feature engineering improves model performance  
- Market accessibility provides additional context  
- Log transformation improves stability  

---

## Challenges and Mitigation

- Data partition bias handled using 5-fold cross validation  
- Target skewness handled using log transformation and clipping  
- Climate variability handled using temporal aggregation  

---

## Project Structure

```
├── Team-1.ipynb
├── Team-1.pdf
├── README.md
```

---

## How to Run

```bash
git clone https://github.com/your-username/repo-name.git
cd repo-name
jupyter notebook Team-1.ipynb
```

---

## Tech Stack

- Python  
- Pandas, NumPy  
- Scikit-learn  
- XGBoost  
- Matplotlib, Seaborn  

---

## Conclusion
The project demonstrates that combining domain knowledge with feature engineering and robust modeling techniques enables effective prediction of farmer income.
