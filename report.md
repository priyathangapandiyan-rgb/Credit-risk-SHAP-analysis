# Interpretable Machine Learning – Credit Risk Prediction (SHAP Analysis)

## 1. Project Overview
This project predicts **credit risk** using the Kaggle “Public credit risk ” dataset. 
Two machine learning models were trained:

- **XGBoost Classifier**
- **RandomForest Classifier**

The best model was interpreted using **SHAP (SHapley Additive exPlanations)** for both global and local interpretability.

---
## 2. Dataset Summary
- **Source:** Public credit risk datasets from **Kaggle / Lending Club / Home Credit**. 
- **Rows:** 32,582  
- **Columns:** 13 
- **Target Column:** `default` (1 = default, 0 = no default)

### Key Feature Groups
- **Personal details** (Age, Income, Employment Length)
- **Loan details** (Amount, Interest Rate, Grade, Intent)
- **Credit history** (Default on File, Credit History Length)
- **Credit history** (Default on File, Credit History Length) Loan status (0 = No Default, 1 = Default)
---
## 3. Preprocessing
- Missing values handled using **median , mean imputation**
- **Outlier Removal**
- **Feature Engineering**
- **Class Imbalance Handling**
- Training/testing split: **80% / 20%**
- Dataset transformed into a numerical matrix for XGBoost/RandomForest
---

## 4. Model Evaluation

### XGBoost Results
- **AUC:** 0.84  
- **F1 Score:** 0.80
- **Precision:** 0.96
- **Recall:** 0.69
- **Hyperparameters:** n_estimators=100, max_depth=4, learning_rate=0.1
  
### Interpretation
- Strong performance for default detection  
- The model shows strong predictive performance. High precision indicates fewer false positives, while the F1 score reflects a good balance between precision and recall.
---

## 5. Global SHAP Analysis

### Top 10 Most Influential Features
Identified from mean absolute **SHAP** values:

1. Person_income	
2. Loan_intent
3. Loan_grade
4. Person_home_ownership
5. Loan_to_income_ratio
6. Loan_percent_income
7. Loan_int_rate
8. Person_age
9. Loan_to_emp_length_ratio
10. Int_rate_to_loan_amt_ratio
11. Person_emp_length
12. Loan_amnt
13. cb_person_cred_hist_length

### Global SHAP Plots
- `plots/2.Global SHAP Plot.png`
- `plots/3.Global features summary SHAP Plot.png`
---
### Compare with Model’s Built-in Feature Importance
- `plots/4.Feature importance plot.png`
---

## 6. Comparative Analysis: Global Feature Importance

### XGBoost Built-in Importance

| Rank | Feature                     | Importance Score |
|------|-----------------------------|------------------|
| 1    | person_income               | 302.0            |
| 2    | loan_intent                 | 174.0            |
| 3    | loan_grade                  | 154.0            |
| 4    | person_home_ownership       | 120.0            |
| 5    | loan_to_income_ratio        | 107.0            |
| 6    | loan_percent_income         | 81.0             |
| 7    | loan_int_rate               | 74.0             |
| 8    | person_age                  | 59.0             |
| 9    | loan_to_emp_length_ratio    | 48.0             |
| 10   | int_rate_to_loan_amt_ratio  | 47.0             |
| 11   | person_emp_length           | 37.0             |
| 12   | loan_amnt                   | 27.0             |
| 13   | cb_person_cred_hist_length  | 19.0             |
---
## SHAP Summary Plot Importance

| Rank | Feature                     | SHAP Impact |
|------|-----------------------------|-------------|
| 1    | loan_grade                  | High        |
| 2    | person_income               | High        |
| 3    | loan_to_income_ratio        | High        |
| 4    | loan_intent                 | Moderate    |
| 5    | person_home_ownership       | Moderate    |
| 6    | loan_percent_income         | Moderate    |
| 7    | loan_int_rate               | Moderate    |
| 8    | person_emp_length           | Moderate    |
| 9    | person_age                  | Low         |
| 10   | loan_to_emp_length_ratio    | Low         |
| 11   | loan_amnt                   | Low         |
| 12   | int_rate_to_loan_amt_ratio  | Low         |
| 13   | cb_person_cred_hist_length  | Low         |
| 14   | cb_person_default_on_file   | Very Low    |
---

##  Key Insights

- **person_income** is consistently ranked highest in both methods — confirming its strong predictive power.
- **loan_grade** has greater impact in SHAP than in XGBoost, suggesting its influence is more nuanced than split frequency reveals.
- **person_emp_length** and **person_home_ownership** show stronger influence in SHAP, highlighting their subtle but consistent effect on credit risk.
- **cb_person_default_on_file** appears in SHAP but not in XGBoost’s top ranks — SHAP captures its marginal but meaningful impact.

---

##  Conclusion

- XGBoost’s built-in metrics are useful for quick feature ranking but may miss deeper patterns.
- SHAP provides richer interpretability, showing both magnitude and direction of feature influence.
- For policy decisions and fairness audits, SHAP is the preferred method for understanding model behavior.




