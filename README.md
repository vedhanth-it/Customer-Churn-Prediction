# 🧠 Customer Churn Prediction Using Machine Learning

## 📘 Project Overview
This project aims to **predict customer churn** — whether a customer will leave (churn) or stay — using various **machine learning algorithms**.  
By identifying at-risk customers early, businesses can take proactive retention measures.

---

## 🎯 Problem Statement
Customer churn is a key business problem in subscription-based industries.  
The objective is to **build a classification model** that predicts whether a customer will churn (`Exited = 1`) or stay (`Exited = 0`) based on demographic, account, and service-related features.

---

## 📂 Dataset Information

**Dataset Name:** `churn.csv`  
**Shape:** ~10,000 rows × 14 columns  
**Target Variable:** `Exited` (1 = churned, 0 = stayed)

### Key Features:
| Feature | Description |
|----------|-------------|
| CustomerId | Unique customer identifier |
| Geography | Customer’s country |
| Gender | Male/Female |
| Age | Customer age |
| Tenure | Number of years with the bank |
| Balance | Account balance |
| NumOfProducts | Number of products used |
| HasCrCard | Whether the customer has a credit card |
| IsActiveMember | Whether the customer is active |
| EstimatedSalary | Estimated annual income |

---

## 🔍 Exploratory Data Analysis (EDA)

### 🧾 General Findings
- No missing values found.
- Mixed data types — numerical and categorical.
- Balanced number of male and female customers.

### 📊 Visualizations
- **Histograms** for all numerical features show right-skewed distributions (Balance, Age).
- **Countplots** for categorical variables (Gender, Geography) reveal class imbalances.
- **Churn Distribution:** Around 20% of customers churned.
- **Heatmap:** High correlation between `Age`, `Balance`, and churn likelihood.

---

## ⚠️ Outlier Detection
- Outliers were identified in `Balance` and `EstimatedSalary` using boxplots.
- Winsorization and scaling techniques were applied to handle skewness and extreme values.

---

## ⚙️ Data Preprocessing
- **Encoding:** Target encoding used for categorical variables (`Geography`, `Gender`).
- **Scaling:** StandardScaler applied to normalize numerical features.
- **Train/Test Split:** 80% training and 20% testing.

---

## 🧩 Model Selection

### Models Evaluated:
1. **Logistic Regression**
2. **Random Forest Classifier**
3. **XGBoost Classifier**

### Evaluation Metrics:
- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC

---

## 📈 Model Performance Summary

| Model | Accuracy | Precision | Recall | F1-score | ROC-AUC |
|--------|-----------|------------|---------|-----------|----------|
| Logistic Regression | 0.80 | 0.74 | 0.62 | 0.68 | 0.83 |
| Random Forest | 0.86 | 0.82 | 0.74 | 0.78 | 0.90 |
| XGBoost | **0.88** | **0.85** | **0.76** | **0.80** | **0.92** |

✅ **XGBoost performed the best** in terms of both accuracy and generalization.

---

## 🔧 Hyperparameter Tuning

- **Random Search CV** used for Random Forest & XGBoost.
- Parameters tuned:
  - `n_estimators`
  - `max_depth`
  - `learning_rate`
  - `min_child_weight`
  - `subsample`
- Best tuned XGBoost model achieved **~89% accuracy** and **ROC-AUC of 0.92**.

---

## 🧾 Confusion Matrix & ROC Curve
- Visualized confusion matrices to identify false positives/negatives.
- ROC curve shows good separation between churned and retained customers.

---

## 🧠 Conclusion
- **XGBoost** outperformed other models with strong classification metrics.
- Age, Balance, and Activity Level are the most influential churn predictors.
- The model can effectively help in **early churn detection** for customer retention strategies.

---

## 🚀 Future Scope
- Implement **SHAP or LIME** for model interpretability.
- Deploy model using **Flask or Streamlit** as a web app.
- Include **time-series behavior** or **customer feedback data** for improved predictions.
- Experiment with **Deep Learning models** for better accuracy.

---

## 🧰 Tech Stack
- Python 🐍
- Pandas, NumPy
- Scikit-learn
- XGBoost
- Matplotlib, Seaborn
- Jupyter Notebook

---
