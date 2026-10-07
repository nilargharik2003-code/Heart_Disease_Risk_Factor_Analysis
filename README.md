# Heart_Disease_Risk_Factor_Analysis
# Heart Disease Risk Factor Analysis using Logistic Regression
## Overview

This project analyzes the Framingham Heart Study dataset to identify demographic, behavioral, and clinical factors associated with the 10-year risk of coronary heart disease. A Logistic Regression model is developed to predict the binary outcome `TenYearCHD`.
## Dataset

The dataset contains 4,240 observations and 15 explanatory variables related to demographic, behavioral, and clinical characteristics.

The target variable is `TenYearCHD`, which indicates whether an individual is at risk of developing coronary heart disease within 10 years.
## Methodology

- Performed data preprocessing and handled missing values using mean/mode imputation.
- Conducted exploratory correlation analysis to examine relationships between variables.
- Checked multicollinearity using Variance Inflation Factor (VIF).
- Removed `sysBP` due to its high correlation with `diaBP`.
- Standardized explanatory variables using `StandardScaler`.
- Split the dataset into training and testing sets.
- Applied SMOTE to address class imbalance in the training data.
- Developed a Logistic Regression model for binary classification.
- ## Model Evaluation

The Logistic Regression model was evaluated using:

- Confusion Matrix
- Accuracy
- Precision
- Recall
- F1-Score
- | Metric | Score |
|--------|-------|
| Accuracy | XX.XX% |
| Precision | XX.XX% |
| Recall | XX.XX% |
| F1-Score | XX.XX% |
## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Statsmodels
- Imbalanced-learn
- ## Repository Contents

- `framingham.csv` — Dataset used for the analysis
- `heart_disease_risk_factor_analysis_logistic_regression.ipynb` — Complete Python implementation
- `README.md` — Project documentation
- ## Key Findings

- Examined relationships among demographic, behavioral, and clinical variables.
- Identified strong correlation between `sysBP` and `diaBP`.
- Used VIF to assess multicollinearity among predictors.
- Addressed the class imbalance in the target variable using SMOTE.
- Evaluated the Logistic Regression model using multiple classification metrics.
