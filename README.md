# 📉 Telcom Customer Churn Prediction

This project predicts customer churn for a telecom company using multiple machine learning models. The goal is to help the business identify customers at risk of leaving so they can take action to retain them.

---

## **Project Overview**

- **Dataset:** Telco customer data with demographics, account details, services, and churn labels.
- **Goal:** Predict whether a customer will churn (`Churn` = Yes or No).
- **Approach:** Train & evaluate different models:  
  - K-Nearest Neighbors (KNN)
  - Random Forest
  - Logistic Regression (with and without class balancing)
  - XGBoost

---

## **Key Steps**

### 1️⃣ **Preprocessing**
- Converted categorical variables with `LabelEncoder`.
- Identified numeric and categorical columns.
- Standardized numerical columns (`tenure`, `MonthlyCharges`, `TotalCharges`) to mean 0, std 1.
- Handled class imbalance with `class_weight='balanced'` (Logistic Regression) and `scale_pos_weight` (XGBoost).

### 2️⃣ **Train-Test Split**
- Used `train_test_split` with `stratify` to preserve churn ratio.
- 80% training, 20% testing.

### 3️⃣ **Modeling**
- Fitted KNN, Random Forest, Logistic Regression, and XGBoost.
- Tuned relevant hyperparameters (like `scale_pos_weight` for XGB).
- Compared results using:
  - Accuracy
  - Precision, Recall, F1-Score
  - Confusion Matrix
  - ROC Curve & AUC

### 4️⃣ **Evaluation**
- Focused on **recall for churners** — catching customers likely to churn is more important than raw accuracy.
- Compared trade-offs for precision vs. recall.

---

## 📊 **Results Summary**

| Model | Accuracy | Churn Recall | Churn Precision |
|-------|----------|---------------|-----------------|
| KNN | ~78% | ~52% | ~60% |
| Random Forest | ~81% | ~49% | ~72% |
| Logistic Regression (balanced) | ~75% | ~80% | ~52% |
| XGBoost | ~76% | ~82% | ~53% |

**Key Insight:**  
XGBoost and balanced Logistic Regression achieve **high churn recall**, which is crucial for retention planning.

---
