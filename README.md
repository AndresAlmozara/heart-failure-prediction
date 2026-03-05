# Cardiovascular Risk Prediction

Machine learning project for predicting cardiovascular disease risk using clinical patient data.

## Project Overview

This project explores clinical and lifestyle variables associated with cardiovascular disease and builds machine learning models to predict patient outcomes.

The objective is to develop a reproducible data science workflow including:

- Exploratory Data Analysis (EDA)
- Data preprocessing and feature engineering
- Baseline machine learning models
- Model evaluation and interpretation

## Problem Statement

Cardiovascular disease is one of the leading causes of death worldwide.  
Early detection of high-risk patients can support preventive healthcare strategies.

This project aims to build a machine learning model capable of predicting the presence of cardiovascular disease based on patient clinical measurements and lifestyle indicators.

## Dataset

The dataset used in this project is the **Cardiovascular Disease Dataset** available on Kaggle.

Source:  
https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset

The dataset contains approximately **70,000 patient records** with clinical and lifestyle features used to predict the presence of cardiovascular disease.

### Features include

- Age
- Height
- Weight
- Gender
- Blood pressure (systolic and diastolic)
- Cholesterol level
- Glucose level
- Smoking status
- Alcohol intake
- Physical activity

### Target variable

- **cardio** → presence or absence of cardiovascular disease (binary classification)

### Download Instructions

Due to licensing restrictions, the dataset is **not included in this repository**.

To reproduce the analysis:

1. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset)

2. Extract the file:
```
cardio_train.csv
```

3. Place it in the following directory:
```
data/raw/cardio_train.csv
```

## Technologies

The project uses the following tools and libraries:

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

## Project Structure

```
Cardiovascular Risk Prediction
│
├── data            # dataset and processed data
├── notebooks       # exploratory analysis and modeling
├── src             # reusable scripts and functions
├── models          # trained models
├── reports         # figures and results
│
├── .gitignore
└── README.md
```

## Objectives

- Practice a complete machine learning workflow
- Apply classification models to medical data
- Develop reproducible data science projects
- Build a professional data science portfolio