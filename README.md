# Cardiovascular Disease Prediction

Machine learning project for predicting cardiovascular disease using clinical and lifestyle patient data.

## Project Overview

This project develops a complete machine learning workflow to predict the presence of cardiovascular disease from structured clinical data. The analysis combines exploratory data analysis, physiologically informed data cleaning, feature engineering, model comparison, hyperparameter tuning, and model interpretation.

The goal is not only to build a predictive model, but also to demonstrate a clear and reproducible end-to-end data science pipeline suitable for portfolio use.

## Problem Statement

Cardiovascular disease is one of the leading causes of death worldwide. Early identification of high-risk patients can support prevention, monitoring, and treatment decisions.

This project aims to build a binary classification model that predicts whether a patient has cardiovascular disease based on clinical measurements and lifestyle-related variables.

## Dataset

The dataset used in this project is the **Cardiovascular Disease Dataset** available on Kaggle.

**Source:**
https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset

The dataset contains approximately **70,000 patient records** and includes demographic, clinical, and behavioral features.

### Original Features

- `age` (in days)
- `gender`
- `height`
- `weight`
- `ap_hi` (systolic blood pressure)
- `ap_lo` (diastolic blood pressure)
- `cholesterol`
- `gluc`
- `smoke`
- `alco`
- `active`
- `cardio` (target)

### Target Variable

- **`cardio`**
  - `0` = no cardiovascular disease
  - `1` = cardiovascular disease

## Data Cleaning

To improve data quality, physiologically implausible observations were removed during the EDA stage.

### Blood Pressure Filtering

Records were removed if:

- `ap_hi <= 0`
- `ap_lo <= 0`
- `ap_hi > 250`
- `ap_lo > 150`
- `ap_hi <= ap_lo`

### Anthropometric Filtering

Records were removed if:

- `height < 120` or `height > 220`
- `weight < 30` or `weight > 200`

After cleaning, the final dataset contained **68,647 observations**.

## Feature Engineering

Several clinically meaningful features were created to improve model signal:

- **`age_years`** = age converted from days to years
- **`BMI`** = body mass index
- **`pulse_pressure`** = `ap_hi - ap_lo`
- **`MAP`** = mean arterial pressure

These engineered variables were included in the modeling stage.

## Workflow

The project is divided into two main notebooks:

### `01_eda.ipynb`

- dataset inspection
- missing value verification
- physiologically informed data cleaning
- feature engineering
- univariate and bivariate analysis
- correlation analysis
- visual exploration of cardiovascular risk patterns

### `02_modeling.ipynb`

- train-test split
- preprocessing and feature scaling
- baseline model training
- model comparison
- hyperparameter tuning
- feature importance analysis
- error analysis
- final model assessment

## Models Evaluated

The following classification models were trained and compared:

- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosting
- XGBoost

## Model Evaluation

Model performance was evaluated using multiple classification metrics:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Confusion Matrix

Because this is a medical prediction problem, recall and ROC-AUC were particularly important for assessing performance.

## Final Model

The final selected model was **Gradient Boosting**.

It achieved the strongest overall performance among the evaluated baseline models, with a **ROC-AUC of approximately 0.80** on the test set.

Hyperparameter tuning was also applied to Gradient Boosting, but it did not produce a meaningful improvement over the baseline configuration. Therefore, the baseline Gradient Boosting model was retained as the final model.

## Key Findings

- **Systolic blood pressure (`ap_hi`)** was the most influential predictor in the final model.
- **Age** and **mean arterial pressure (`MAP`)** also contributed substantially to prediction.
- Tree-based ensemble methods outperformed the single Decision Tree and slightly outperformed Logistic Regression.
- Hyperparameter tuning produced negligible gains, suggesting that the baseline Gradient Boosting model was already well suited to the dataset.

## Project Structure

```text
cardiovascular-disease-prediction/
│
├── data/
│   ├── raw/
│   ├── processed/
│   └── external/
│
├── notebooks/
│   ├── 01_eda.ipynb
│   └── 02_modeling.ipynb
│
├── .gitignore
├── pyproject.toml
├── README.md
└── requirements.txt
```

## Installation

Clone the repository and install the dependencies:

```bash
git clone https://github.com/AndresAlmozara/cardiovascular-disease-prediction.git
cd cardiovascular-disease-prediction
pip install -r requirements.txt
```

## Dataset Setup

Due to licensing restrictions, the dataset is not included in this repository.

To reproduce the project:

1. Download the dataset from Kaggle:
   https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset

2. Extract the file:

```text
cardio_train.csv
```

3. Place it in:

```text
data/raw/cardio_train.csv
```

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- XGBoost
- Jupyter Notebook

## Future Improvements

Possible next steps for extending the project include:

- threshold optimization to better balance false positives and false negatives
- model calibration
- additional feature engineering
- external validation on independent datasets
- migration of preprocessing steps into reusable scripts or configurable pipelines

## Author

**Andrés Almozara García**
GitHub: https://github.com/AndresAlmozara
