# Insurance Charges Prediction

This project builds a machine learning model to predict insurance charges based on various features such as age, BMI, smoking status, and region. The dataset is preprocessed, and a linear regression model is trained and validated.

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Dataset](#dataset)
3. [Preprocessing](#preprocessing)
4. [Model Training](#model-training)
5. [Validation](#validation)
6. [Requirements](#requirements)
7. [Usage](#usage)
8. [Results](#results)

---

## Project Overview

The objective of this project is to predict the insurance charges of individuals based on demographic and health-related attributes. A linear regression model is used to understand the relationship between the input features and the target variable (`charges`).



---

## Preprocessing

The dataset undergoes several preprocessing steps:
1. **Missing Value Imputation**:
   - Mean imputation for numerical columns (`age`, `bmi`, `children`, `charges`).
   - Mode imputation for categorical columns (`sex`, `smoker`, `region`).
2. **Feature Encoding**:
   - Convert categorical variables (`sex`, `smoker`) into numerical representations.
   - Convert `region` into dummy variables, excluding the first category to avoid multicollinearity.
3. **Scaling**:
   - StandardScaler is used to scale features for optimal model performance.

---

## Model Training

A **Linear Regression** model is trained using the preprocessed dataset. The target variable is `charges`, and the features include:
- Numerical columns: `age`, `bmi`, `children`
- Encoded categorical columns: `sex`, `smoker`, `region_<dummy_variables>`

The model is evaluated on the training dataset using the **R-squared** metric.

---

## Validation

A separate validation dataset (`validation_dataset.csv`) is used to evaluate the trained model. The same preprocessing steps are applied to this dataset before predictions are made.

**Predictions** are scaled back and adjusted:
- Minimum insurance charge is capped at `1000` for realistic predictions.

