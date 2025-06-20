# Deepflow
#  Bluebook for Bulldozers - Sale Price Prediction
---

## 🧠 Project Objective

The goal of this machine learning project is to **predict the future sale price of bulldozers** given various features like usage, machine specifications, and sale history. The problem is a **time-aware regression task** and requires careful **data preprocessing** due to the presence of **missing values, categorical columns, and time-based features**.

---

## 📌 Project Status: 

I’ve trained and validated multiple models and generated predictions for the test data. All components, including data cleaning, feature engineering, and model evaluation, have been completed.

---

## 🧪 Data

The data was sourced from the [Kaggle Bluebook for Bulldozers](https://www.kaggle.com/c/bluebook-for-bulldozers/data) competition.

### Files Used:

- `Train.csv`: Training data (until end of 2011)
- `Valid.csv`: Validation data (Jan 2012 – Apr 2012)
- `Test.csv`: Final test data (May 2012 – Nov 2012)

### Target Variable:

- `SalePrice` – The price at which a bulldozer was sold at auction.

---

## 🛠 Features

Extensive feature engineering was performed:
- Parsed `saledate` into components: `saleYear`, `saleMonth`, `saleDay`, `saleDayOfWeek`, `saleDayOfYear`
- Derived feature: `machine_age = saleYear - YearMade`
- Handled string columns using category encoding + `_is_missing` binary flags
- Handled numeric missing values with median imputation
- Removed columns with >90% missing data
- Dropped high-cardinality identifiers like `SalesID`, `MachineID`

Kaggle's [Data Dictionary](https://docs.google.com/spreadsheets/d/18ly-bLR8sbDJLITkWG7ozKm8l3RyieQ2Fpgix-beSYI/edit?usp=sharing) provides details on all original features.

---

## 🔍 Methods Used

- **Exploratory Data Analysis (EDA)**
- **Missing Value Treatment**
- **Feature Engineering**
- **Encoding & Transformation**
- **Model Evaluation**

---

## 🤖 Models Applied

| Model                | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| `LinearRegression`  | Baseline regression model for initial evaluation                            |
| `RandomForestRegressor` | Ensemble model with `n_estimators=100`, `max_samples=10000` for faster training |

---

## 🧮 Evaluation Metrics

We focused on **RMSLE (Root Mean Squared Logarithmic Error)**, which is ideal for targets with large value ranges like price.

Additional metrics:
- `MAE` – Mean Absolute Error
- `R²` – Coefficient of Determination

---

## 📊 Evaluation

| Metric              | Score     |
|---------------------|-----------|
| Training RMSLE      |  0.25307 |
| Validation RMSLE    |  0.28722 |
| Final Model Used    | RandomForestRegressor |

---

## 📁 Project Structure
├── final_model.ipynb # Main notebook with full pipeline
├── test_predictions.csv # Submission file with SalesID and predicted SalePrice
├── README.md # This file
├── data/ # Folder for Train.csv, Valid.csv, Test.csv
├── preprocess.py # (optional) Preprocessing functions


---

## ⚙️ Technologies Used

- Python 3
- pandas, numpy
- scikit-learn
- matplotlib, seaborn
- Jupyter Notebook

---



