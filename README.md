# 📊 Telco Customer Churn Prediction

## 🎯 Project Goal

The goal of this project is to build a machine learning model that can accurately **predict customer churn** for a telecom company. By identifying customers who are likely to leave, the company can take proactive steps to retain them, minimize revenue loss, and improve long-term customer satisfaction.

---

## 📁 Dataset Overview

The dataset contains information about customer demographics, account details, and service usage, including:

- **Demographics**: gender, senior citizen status, dependents, etc.
- **Services**: phone, internet, online security, tech support, etc.
- **Account**: tenure, monthly charges, payment method, contract type
- **Target Variable**: `Churn` (Yes/No)

---

## 📊 Exploratory Data Analysis (EDA)

### 🔍 Key Insights:

1. **Gender vs Churn**
   - Churn rates are almost equal for male and female customers.
   - **Gender is not a strong predictor** of churn.

2. **Senior Citizen vs Churn**
   - **Senior citizens churn more** than younger customers.

3. **Payment Method vs Churn**
   - **Electronic Check** users show higher churn than users of mailed checks or automatic payments.

4. **Contract Type vs Churn**
   - Customers with **month-to-month contracts churn the most**.
   - **Long-term contracts (1 or 2 years)** are associated with lower churn.

5. **Dependents vs Churn**
   - Customers with **dependents churn significantly less**.

6. **Paperless Billing vs Churn**
   - Churn is higher among those who opted for **paperless billing**.

7. **Tech Support vs Churn**
   - Customers with **tech support** churn less, emphasizing the value of good service.

8. **Device Protection vs Churn**
   - Having **device protection** is associated with lower churn.

9. **Online Security vs Churn**
   - **Churn is higher** among those **without online security**.

10. **Monthly Charges vs Churn**
    - Customers who churned tend to have **higher monthly charges**.

11. **Tenure vs Churn**
    - Customers with **shorter tenure are more likely to churn**.
    - Median tenure for churned users is ~10 months, compared to ~40 months for retained users.

---

## 🤖 Modeling Summary

We evaluated several models to predict customer churn:

| Model                   | Churn Recall | Churn Precision | Churn F1-score | Accuracy |
|------------------------|---------------|------------------|----------------|----------|
| **Logistic Regression** | 0.57          | 0.64             | 0.60           | **0.80**  |
| **Random Forest**       | 0.75 ✅        | 0.54             | 0.63           | 0.77     |
| **XGBoost**             | 0.80 ✅        | 0.51             | 0.62           | 0.74     |
| **Voting Ensemble**     | 0.75 ✅        | 0.52             | 0.61           | 0.75     |
| **Stacking Ensemble**   | 0.78 ✅        | 0.52             | 0.62           | 0.75     |

---

## ✅ Conclusion & Recommendation

- If your goal is to **catch as many churners as possible**, use:
  - ✅ **XGBoost** or **Stacking Ensemble (meta-model: Logistic Regression)**

- If you prefer **simpler, interpretable models** and are okay with slightly lower recall:
  - ✅ **Logistic Regression** performs surprisingly well and is easy to deploy.

- **Tenure**, **contract type**, **monthly charges**, and **service features** like `TechSupport`, `OnlineSecurity`, and `DeviceProtection` are **key drivers** of churn and should be prioritized in modeling and business actions.

---

## 📌 Next Steps

- Perform hyperparameter tuning and cross-validation for top models.
- Calibrate classification thresholds to balance precision vs recall.
- Deploy model and monitor drift or feature distribution changes over time.
