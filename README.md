# Heart_Disease_Risk_Factor_Analysis
# Heart Disease Risk Factor Analysis ❤️

This project focuses on analyzing risk factors associated with the **10-year risk of coronary heart disease (CHD)** using **Logistic Regression**. The analysis includes data preprocessing, missing-value imputation, correlation analysis, multicollinearity assessment using VIF, feature scaling, class balancing using SMOTE, and evaluation of the Logistic Regression model.

## 💾 Data Description

The analysis uses the **Framingham Heart Study dataset**, containing information about demographic characteristics, medical history, lifestyle factors, and clinical measurements.

### Dataset Information

* **Number of observations:** 4240
* **Number of variables:** 16
* **Target Variable:** `TenYearCHD`
* **Objective:** Predict whether an individual is at risk of developing coronary heart disease within the next 10 years.

### Target Variable

* **`TenYearCHD`**: Binary target variable indicating 10-year coronary heart disease risk:
    * `0` → No CHD within 10 years
    * `1` → CHD within 10 years

The dataset contains demographic, behavioural, and medical variables such as age, smoking status, blood pressure, cholesterol, BMI, heart rate, and glucose levels.

***

## 🛠️ Methodology Summary

The machine learning pipeline involved several key stages:

### 1. Data Preprocessing

* Loaded the Framingham dataset using **Pandas**.
* Examined the data types, missing values, and class distribution.
* The dataset initially contained missing values in variables such as `education`, `cigsPerDay`, `BPMeds`, `totChol`, `BMI`, `heartRate`, and `glucose`.
* Numerical variables were imputed using the **mean**.
* Categorical/binary variables were imputed using the **most frequent value (mode)**.
* After imputation, the dataset contained **no missing values**.

### 2. Correlation Analysis

* A correlation matrix was created for the numerical variables.
* The analysis identified a high correlation between `sysBP` and `diaBP`.
* Since these variables provide overlapping blood-pressure information, `sysBP` was removed to reduce potential multicollinearity.

### 3. Multicollinearity Analysis

* **Variance Inflation Factor (VIF)** was calculated for the remaining numerical predictors.
* The resulting VIF values were close to 1, indicating **low multicollinearity** among the retained numerical features.

### 4. Feature Scaling

* The target variable `TenYearCHD` was separated from the predictor variables.
* The predictors were standardized using **StandardScaler**.
* This transformed the features to a common scale before fitting the Logistic Regression model.

### 5. Handling Class Imbalance

The target variable was highly imbalanced:

* **No CHD:** 3596 observations
* **CHD:** 644 observations

The data was split into:

* **80% Training Data**
* **20% Testing Data**

**SMOTE (Synthetic Minority Over-sampling Technique)** was applied **only to the training data** to balance the two classes.

Before SMOTE:

* Class 0: 2890
* Class 1: 502

After SMOTE:

* Class 0: 2890
* Class 1: 2890

### 6. Model Training

* A **Logistic Regression** model was trained using the SMOTE-balanced training dataset.
* Predictions were generated on the original, un-resampled test dataset.

### 7. Model Evaluation

The model was evaluated using:

* **Confusion Matrix**
* **Precision**
* **Recall**
* **F1-Score**
* **Accuracy**

***

## 📊 Results Summary

### Class Distribution

| Class | Observations |
| :--- | ---: |
| **No CHD (0)** | 3596 |
| **CHD (1)** | 644 |

### Model Performance

| Metric | Class 0 – No CHD | Class 1 – CHD |
| :--- | :---: | :---: |
| **Precision** | 0.89 | 0.26 |
| **Recall** | 0.68 | 0.57 |
| **F1-Score** | 0.77 | 0.36 |

### Overall Performance

| Metric | Result |
| :--- | :---: |
| **Accuracy** | 66% |
| **Macro F1-Score** | 0.56 |
| **Weighted F1-Score** | 0.70 |

### Confusion Matrix

| | Predicted 0 | Predicted 1 |
| :--- | ---: | ---: |
| **Actual 0** | 477 | 229 |
| **Actual 1** | 61 | 81 |

***

## 🔍 Observation

The original dataset showed a substantial **class imbalance**, with 3596 individuals without CHD and only 644 individuals with CHD. Therefore, SMOTE was applied to the training data to balance the two classes before fitting the Logistic Regression model.

The correlation analysis showed a strong relationship between `sysBP` and `diaBP`. `sysBP` was therefore removed from the model, and the subsequent VIF analysis showed that the remaining numerical predictors had relatively low multicollinearity.

The Logistic Regression model achieved an overall **accuracy of 66%** on the held-out test set.

For the CHD class (`TenYearCHD = 1`), the model achieved a **recall of 0.57**, meaning that it correctly identified 57% of the individuals who developed CHD within 10 years in the test set. The corresponding precision was **0.26**, while the F1-score was **0.36**.

The model therefore showed better performance in identifying individuals without CHD than those with CHD. This indicates that, despite applying SMOTE to address class imbalance, predicting the minority CHD class remains challenging.

Overall, the analysis demonstrates the use of **Logistic Regression, correlation analysis, VIF, feature scaling, and SMOTE** for studying and predicting 10-year coronary heart disease risk.

***

## 🧰 Tools & Libraries

* **Python**
* **Pandas** – Data loading and data manipulation
* **NumPy** – Numerical computations
* **Matplotlib** – Data visualization
* **Seaborn** – Correlation analysis and visualization
* **Scikit-learn** – Logistic Regression, preprocessing, scaling, and model evaluation
* **Statsmodels** – Statistical analysis and VIF calculation
* **Imbalanced-learn** – SMOTE for handling class imbalance
