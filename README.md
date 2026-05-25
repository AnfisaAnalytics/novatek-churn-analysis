# 📉 Customer Churn Analysis — NovaTel Telecom


📓 View the full analysis notebook → [telco_churn_analysis](https://github.com/AnfisaAnalytics/novatek-churn-analysis/blob/33743d4f5b05fa348d127ae96d7360095d2ca0a6/telco_churn_analysis.ipynb)


<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white"/>
  <img src="https://img.shields.io/badge/scikit--learn-ML-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white"/>
  <img src="https://img.shields.io/badge/pandas-Data-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
  <img src="https://img.shields.io/badge/Status-Complete-2ea44f?style=for-the-badge"/>
</p>

<br>

> **End-to-end churn prediction project** — from raw data through EDA, feature engineering, and machine learning modelling to actionable business recommendations. Built as a portfolio project to demonstrate real-world data analysis skills.

---

## 📌 Problem Statement

Customer churn is one of the most expensive problems in the telecom industry — acquiring a new customer costs 5–7× more than retaining an existing one. **NovaTel** (fictional telecom company) wants to identify which customers are most likely to leave so the retention team can proactively intervene.

**Goal:** Build a model that predicts churn with high accuracy and extract actionable insights from the data.

---

## 📊 Dataset

| Property | Value |
|---|---|
| Rows | 7,043 customers |
| Features | 20 (demographics, services, contract, billing) |
| Target | `churn` — Yes / No |
| Churn rate | ~26% |
| Source | Synthetic data generated with `generate_churn_data.py`, modelled after the [IBM Telco Churn benchmark](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) |

**Key features include:** contract type, internet service, payment method, tenure, monthly charges, tech support, online security, and more.

---

## 🗂 Project Structure

```
novatek-churn-analysis/
│
├── 📓 telco_churn_analysis.ipynb   ← Main analysis notebook
├── 🐍 generate_churn_data.py       ← Synthetic data generator
│
├── data/
│   └── telco_churn_raw.csv         ← Raw dataset (7 043 rows)
│
├── figures/                        ← All charts saved here
│   ├── 01_churn_overview.png
│   ├── 02_numerical_features.png
│   ├── 03_categorical_churn.png
│   ├── 04_tenure_segments.png
│   ├── 05_correlation_heatmap.png
│   ├── 06_roc_curves.png
│   ├── 07_confusion_matrices.png
│   ├── 08_feature_importance.png
│   └── 09_lr_coefficients.png
│
├── requirements.txt
└── README.md
```

---

## 🔍 Analysis Overview

The notebook is structured as a complete analytical workflow:

### 1. Data Cleaning
- Converted empty strings in `total_charges` to `NaN`
- Median imputation for 3 columns with missing values
- Duplicate check and `senior_citizen` label formatting

### 2. Exploratory Data Analysis
- Overall churn rate breakdown
- Distributions of `tenure_months`, `monthly_charges`, `total_charges` by churn status
- Churn rate across 9 categorical features (contract, internet type, payment method, etc.)
- Churn by tenure segment — revealing the critical first-year drop-off
- Correlation heatmap

### 3. Feature Engineering
- Label Encoding for all categorical variables
- StandardScaler for Logistic Regression
- Stratified 80/20 train-test split

### 4. Modelling & Evaluation
Three models trained and compared with 5-fold cross-validated ROC-AUC:

| Model | CV ROC-AUC | Test ROC-AUC |
|---|---|---|
| Logistic Regression | 0.831 | 0.836 |
| Random Forest | 0.818 | 0.818 |
| Gradient Boosting | 0.826 | 0.828 |

### 5. Feature Importance
Top churn predictors identified from both Gradient Boosting and Logistic Regression coefficients.

---

## 💡 Key Findings

| # | Finding |
|---|---|
| 🔴 | **Month-to-month** customers churn at ~42% vs ~11% on two-year contracts |
| 🔴 | **Fiber optic** internet users churn significantly more than DSL users |
| 🟠 | **Electronic check** payment is strongly associated with churn |
| 🟠 | Customers with **no tech support** or **no online security** churn 2× more |
| 🟠 | **New customers (0–12 months)** are the highest-risk group — churn drops sharply after year 2 |
| 🟡 | **Senior citizens** churn ~10 percentage points more than non-seniors |

---

## 🚀 How to Run

**1. Clone the repo**
```bash
git clone https://github.com/YOUR_USERNAME/novatek-churn-analysis.git
cd novatek-churn-analysis
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Create the `figures/` folder**
```bash
mkdir figures
```

**4. Open and run the notebook**
```bash
jupyter notebook telco_churn_analysis.ipynb
```
Then: **Kernel → Restart & Run All**

> To regenerate the dataset from scratch, run `python generate_churn_data.py` first.

---

## 🛠 Tech Stack

| Tool | Purpose |
|---|---|
| **Python 3.10+** | Core language |
| **pandas / numpy** | Data manipulation |
| **matplotlib / seaborn** | Visualisation |
| **scikit-learn** | ML modelling & evaluation |
| **Jupyter Notebook** | Interactive analysis |
| **Faker** | Synthetic data generation |

---

## 📁 Requirements

```
pandas
numpy
matplotlib
seaborn
scikit-learn
faker
jupyter
nbformat
```

Install all at once:
```bash
pip install -r requirements.txt
```

---

## 👩‍💻 About

This project was built as a **portfolio piece** to demonstrate end-to-end data analysis and machine learning skills relevant to freelance data work — covering data cleaning, exploratory analysis, feature engineering, model comparison, and translating results into business recommendations.

**Skills demonstrated:** Python · EDA · Data Cleaning · Machine Learning · Data Visualisation · Business Communication

---

*Feel free to fork, use, or reach out with questions.*
