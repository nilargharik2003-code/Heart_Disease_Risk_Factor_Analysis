# Heart_Disease_Risk_Factor_Analysis
# Heart Disease Risk Factor Analysis using Logistic Regression

## Overview

This project analyzes the Framingham Heart Study dataset to identify demographic, behavioral, and clinical factors associated with the 10-year risk of coronary heart disease (TenYearCHD).

A Logistic Regression model is developed to predict the binary outcome `TenYearCHD`.

## Dataset

The dataset contains **4,240 observations** and **16 columns**, including **15 explanatory variables** and the target variable `TenYearCHD`.

The features include:

- Demographic factors: age, sex, education
- Behavioral factors: current smoking status, cigarettes per day
- Clinical factors: blood pressure, cholesterol, BMI, heart rate, glucose, diabetes, etc.
- Target: `TenYearCHD` — 10-year risk of coronary heart disease

The target variable is imbalanced, with:
- 3,596 observations with `TenYearCHD = 0`
- 644 observations with `TenYearCHD = 1`

## Methodology

### 1. Data Preprocessing

- Examined the dataset structure and missing values.
- Applied mean imputation to numerical variables.
- Applied mode imputation to categorical variables.
- Created a cleaned dataset after handling missing observations.

### 2. Correlation Analysis

A correlation matrix was used to examine relationships between numerical predictors.

`sysBP` and `diaBP` showed high correlation. `sysBP` was removed to reduce potential multicollinearity.

### 3. Multicollinearity Analysis

Variance Inflation Factor (VIF) was calculated for the numerical predictors. The resulting VIF values were close to 1, indicating no significant multicollinearity among the remaining predictors.

### 4. Feature Scaling

The explanatory variables were standardized using `StandardScaler`.

### 5. Handling Class Imbalance

Since the target variable was highly imbalanced, **SMOTE (Synthetic Minority Oversampling Technique)** was applied to the training data to balance the two classes.

SMOTE was applied only to the training set, while the original test set was retained for evaluation.

### 6. Logistic Regression

A Logistic Regression model was trained using the resampled training data to predict `TenYearCHD`.

## Model Evaluation

The model was evaluated on the original test set using:

- Confusion Matrix
- Accuracy
- Precision
- Recall
- F1-Score

The classification report provides the detailed performance of the model for both classes.

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Statsmodels
- Imbalanced-learn (SMOTE)

## Repository Contents

- `framingham.csv` — Framingham Heart Study dataset
- `heart_disease_risk_factor_analysis_logistic_regression.ipynb` — Complete Python implementation and analysis
- `README.md` — Project documentation
