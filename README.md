# 📊 Customer Churn Prediction 

---

## 🧠 Project Overview

Customer churn is one of the most critical challenges in subscription and telecom industries.  
This project aims to **develop, validate, and deploy a predictive model** that identifies customers likely to leave (churn) using statistical and machine learning techniques.

**Objective:**  
- To analyze customer behavior using data-driven methods.  
- To develop a **CHAID-style Decision Tree** and **Logistic Regression model** for churn prediction.  
- To evaluate models using **Accuracy, ROC-AUC, Lift, and Gains charts**.  
- To demonstrate a working deployment pipeline using `Joblib`.


## 🧩 Dataset

**Source:** [Kaggle – Telco Customer Churn Dataset](https://www.kaggle.com/blastchar/telco-customer-churn)

**Records:** 7,043 customers  
**Features:** 21 (demographic, account, and service details)

### Data Cleaning Performed:
- Removed duplicates and irrelevant identifiers (`customerID`)  
- Converted `Churn` to numeric (`Yes` → 1, `No` → 0)  
- Converted `TotalCharges` to numeric and imputed missing values  
- Removed whitespace from string entries  
- Verified no missing or inconsistent data  

🧾 **Cleaned dataset:** `churn_outputs/cleaned_telco_churn.csv`

---

## ⚙️ Model Development

### 1. CHAID-Style Decision Tree
- Implemented using `DecisionTreeClassifier` (Entropy criterion as CHAID equivalent)  
- Extracted interpretable business rules:
  - Month-to-month + No online security + Short tenure → High churn risk  
  - One-year or two-year contracts → Low churn risk  

### 2. Logistic Regression
- Baseline statistical model for churn prediction  
- Provided highest AUC (0.84) and accuracy (0.80)

---

## 📈 Model Evaluation

| Model | Accuracy | ROC-AUC | Cross-Validation |
|--------|-----------|----------|------------------|
| Logistic Regression | **0.800** | **0.840** | 0.79 |
| Decision Tree (CHAID-style) | 0.786 | 0.824 | 0.78 |

- **ROC Curve:** Logistic Regression slightly outperformed Decision Tree.  
- **Lift & Gains Charts:** Top 10% of predictions captured over 2× more churners than random targeting.

---

## 🚀 Model Deployment

Deployment was implemented using **Joblib** for serialization.


