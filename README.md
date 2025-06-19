# Deepflow
# 🚜 Bluebook for Bulldozers - Sale Price Prediction

This project focuses on predicting the **sale price of used bulldozers** using historical auction data provided by **Kaggle**. The goal is to build a machine learning model that accurately estimates prices based on various features like product ID, usage, location, and date of sale.

---

## 📁 Dataset Overview

- **Source:** [Kaggle: Bluebook for Bulldozers](https://www.kaggle.com/competitions/bluebook-for-bulldozers/)
- **Files used:**
  - `Train.csv`
  - `Valid.csv`
  - `Test.csv`

- **Target variable:** `SalePrice`

---

## ⚙️ Approach

### 1. **Preprocessing**
- Converted `saledate` to datetime format and extracted temporal features like:
  - `saleYear`, `saleMonth`, `saleDay`, `saleDayOfWeek`, and `saleDayOfYear`
- Derived feature: `machine_age = saleYear - YearMade`
- Removed high-cardinality ID columns (`SalesID`, `MachineID`)
- Dropped columns with more than 90% missing values
- Handled missing values:
  - Numerical columns → filled with **median**
  - Categorical columns → encoded using `.cat.codes` and added `_is_missing` flags

### 2. **Modeling**
- Used **RandomForestRegressor** from Scikit-learn
- Set `max_samples=10000` to speed up training with large data
- Evaluation metric used: **Root Mean Squared Logarithmic Error (RMSLE)**

### 3. **Prediction**
- Generated predictions on test set
- Created submission file: `test_predictions.csv` in required format

---

## 📊 Evaluation

| Metric              | Score     |
|---------------------|-----------|
| Training RMSLE      | *(your score)* |
| Validation RMSLE    | *(your score)* |
| Final Model Used    | RandomForestRegressor |

---

## 📦 Libraries Used

- pandas
- numpy
- matplotlib / seaborn
- scikit-learn
- xgboost (optional)
- catboost (optional)

---

## 📁 Repository Structure

