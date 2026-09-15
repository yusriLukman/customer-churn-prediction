# End-to-End E-Commerce Customer Analytics & Retention Strategy

A comprehensive Machine Learning and Analytics project designed to predict customer churn, identify core behavioral attrition drivers, and deliver risk-scored data exports for targeted business retention strategies.

**Tech Stack & Tools:** Python 3.9+ | Scikit-Learn | Imbalanced-Learn (SMOTE) | Pandas | NumPy | Matplotlib & Seaborn

---

## Project Overview

Customer churn poses a significant challenge in the competitive e-commerce landscape. Acquiring new customers is substantially more expensive than retaining existing ones. This project addresses customer attrition by deploying a Random Forest Classifier that prioritizes high **Recall** for churned customers, allowing CRM teams to intervene before high-risk users churn.

The technical workflow follows a structured **Three-Pillar Architecture**:
1. **Data Preprocessing, Visual EDA & Class Balancing**
2. **Predictive Modeling & Performance Evaluation**
3. **Feature Importance Analysis & Strategic Business Recommendations**

---

## Dataset

* **Source:** [E-Commerce Customer Churn Dataset (Kaggle)](https://www.kaggle.com/datasets/samuelsemaya/e-commerce-customer-churn)
* **Scope:** Transactional customer records including demographic characteristics, interaction complaints, order preferences, and tenure history.

---

## Technical Architecture & Methodology

### Pillar 1: Data Preprocessing, Visual EDA & Class Balancing
* **Data Cleaning:** Imputed missing values using feature medians and removed non-predictive identifiers (`CustomerID`).
* **Visual EDA:** Explored key bivariate relationships (`Complain`, `PreferedOrderCat`, and `Tenure`) against target churn labels.
* **Encoding & Balancing:** Converted categorical features using One-Hot Encoding (`pd.get_dummies`), applied an 80/20 stratified train-test split, and resolved target class imbalance using **SMOTE** strictly on the training set to prevent data leakage.

### Pillar 2: Predictive Modeling & Performance Evaluation
* **Model Selection:** Trained a `RandomForestClassifier` on the SMOTE-resampled training set.
* **Metrics Focus:** Evaluated predictive capability on unseen test data prioritizing **Recall** and **ROC-AUC Score** to minimize False Negatives.

### Pillar 3: Feature Importance Analysis & Strategic Business Recommendations
* **Feature Drivers:** Extracted top feature importance metrics to highlight operational focus areas (e.g., Tenure, Complaint Status).
* **Data Export:** Combined model probability outputs into a consolidated risk-scored output file (`customer_churn_predictions.csv`) sorted by high-risk churn probabilities.

---

## Key Results & Insights

* **Primary Churn Drivers:** Tenure length, complaint history, and specific product category interactions emerged as the strongest predictors of customer defect.
* **Actionable Output:** Generated automated risk probability scores for each test customer, enabling marketing teams to deploy targeted retention offers directly to users with high churn probability (>70%).

---

## Repository Structure

```text
├── assets/
│   ├── eda_churn_factors.png        
│   └── feature_importance.png       
├── customer_churn_prediction.ipynb  
├── customer_churn_predictions.csv   
└── README.md                        
