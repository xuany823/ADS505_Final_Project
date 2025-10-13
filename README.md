# ADS505_Final_Project
# Don't Stop the Music: Predicting Spotify User Churn

## Overview
This project explores how machine learning can help **Spotify** predict which users are likely to churn and take proactive retention actions.  
Using behavioral, demographic, and engagement data, we developed and compared six supervised learning models to identify patterns that signal user disengagement.

The goal is to help Spotify **shift from reactive churn management to proactive user retention** by turning data-driven insights into actionable business strategies.

---

## Business Context
As digital music platforms become increasingly competitive, user retention has become Spotify’s key growth strategy.  
Churn — when listeners stop using or unsubscribe from the platform — directly impacts revenue, ad engagement, and brand loyalty.

Our project addresses this challenge by leveraging data science to:
- Identify high-risk listeners before they leave.  
- Reveal behavioral drivers behind churn (e.g., ad exposure, skip rate, offline listening).  
- Support personalized retention strategies such as targeted offers and curated playlists.

---

## Objectives
**Goal:** Identify Spotify users most likely to churn based on behavioral and engagement data.  
**Approach:** Apply multiple supervised classification models and compare performance metrics.  
**Business Value:** Enable data-driven decisions for user retention and growth.  
**Strategic Outcome:** Help Spotify predict churn early and take proactive action to retain listeners.

---

## Dataset
- **Source:** Spotify Analysis Dataset 2025 (Kaggle)  
- **Size:** 8,000 user records  
- **Features:** 12 variables across demographics, device type, subscription plan, and engagement behavior  
- **Target Variable:** `is_churned` – indicates whether a user has unsubscribed or become inactive  
- **Imbalance:** 26% churners vs. 74% active users (handled via SMOTE)

---

## Methodology

### 1. Data Preprocessing
- One-hot encoding for categorical variables  
- StandardScaler for numerical features  
- SMOTE applied to balance the target variable  
- Train/test split: 75/25 with stratified sampling  

### 2. Modeling Pipeline
All models were trained within a unified **scikit-learn + imbalanced-learn** pipeline:  
`Scaler → SMOTE → Classifier`

### 3. Models Developed
- Logistic Regression  
- Decision Tree  
- Random Forest  
- K-Nearest Neighbors (KNN)  
- XGBoost  
- Neural Network (MLPClassifier)

### 4. Model Evaluation
- Accuracy, Precision, Recall, F1-Score, ROC-AUC  
- ROC Curves, Gain Charts, Confusion Matrices for visualization  
- 5-Fold Cross-Validation using `GridSearchCV()` (tuned in development notebook)

---

## Key Findings
- **XGBoost** achieved the best ROC–AUC (0.548), outperforming other models slightly.  
- **Random Forest** delivered balanced and interpretable results.  
- **Logistic Regression** provided higher recall, identifying more churners at the expense of precision.  
- Overall, results suggest that current user behavior features offer limited predictive power, highlighting the need for richer engagement and temporal data.

---

## Business Insights
- Churn correlates strongly with **high skip rates**, **increased ad exposure**, and **low offline listening activity**.  
- Targeting the **top 30% of users ranked by churn probability** could significantly improve retention efforts.  
- Predictive models can guide Spotify’s marketing and product teams to personalize re-engagement strategies — such as reducing ad load or offering curated playlists.

---

##  Future Work
- Expand dataset to include **time-series behavior trends** (session frequency, playlist diversity).  
- Apply **automated hyperparameter optimization** and extend **cross-validation** to improve model generalization.  
- Implement **SHAP analysis** for explainability and feature importance transparency.  
- Deploy churn prediction dashboard for real-time business monitoring.

---

## Team
**Group 11 – University of San Diego, ADS 505 (Applied Data Science)**  
- **Michelle Wang:** Pipeline design, data preprocessing, model evaluation & visualization  
- **Lei (Larry) Lin:** Exploratory Data Analysis, correlation analysis, data visualization  
- **Michael Ha:** Model validation, cross-validation tuning, business insights integration  

---

##  Tech Stack
- **Languages:** Python  
- **Libraries:** pandas, numpy, scikit-learn, imbalanced-learn, xgboost, matplotlib, seaborn  
- **Tools:** Jupyter Notebook, GitHub, Tableau (for data storytelling)

---

## Reference
Géron, A. (2023). *Hands-on machine learning with scikit-learn, Keras, and TensorFlow* (3rd ed.). O’Reilly Media.

---

## Contact
For questions or collaboration, please reach out via:  
📧 **Michelle Wang** – [LinkedIn](https://www.linkedin.com/) | [GitHub](https://github.com/xuany823)
