# Descriptions of local SHAP explanations

## 1. Local SHAP Analysis for 5 Loan Applications
- Select **3 high-risk** and **2 low-risk** samples

## SHAP Dependence Plot
- `plots/5.SHAP Dependance plot.png`

## Force plots for risk samples
- `plots/6.Force plot for global fearures.png`

---

## 2. Local SHAP Analysis

Three specific instances were analyzed:

### 2.1 False Negative (Actual = Default, Predicted = No Default)
Reasons for misclassification:
- Large recent payments outweighed indicators of debt
- Model perceived financial recovery, reducing predicted risk

### 2.2 False Positive (Actual = No Default, Predicted = Default)
Reasons:
- High outstanding bill plus multiple delayed payments
- Low recent payments strengthened default suspicion

### 2.3 Borderline Correct Prediction
- Probability close to 0.5  
- Balanced signals: moderate payments, moderate bills  
- No dominant feature → borderline prediction


# 🔍 Local SHAP Explanations: Force Plot Narratives

## Case 1: High-Risk Applicant
- **Base Value:** `0.0`  
- **Model Output:** `6.63`  
- **🔴 Features Increasing Risk:**
  - `person_home_ownership = 3.0`
  - `person_income = 130000.0`
  - `loan_percent_income = 0.83`
  - `loan_to_income_ratio = 0.13`
- **🔵 Features Decreasing Risk:**
  - `loan_grade = 0.0`
- **Narrative:**  
  Despite high income, the model sees this applicant as high risk due to a high loan burden and ownership status. Only the loan grade helps reduce the risk slightly, but not enough to offset the upward pressure.
---

## Case 2: High-Risk Applicant
- **Base Value:** `0.0`  
- **Model Output:** `3.29`  
- **🔴 Features Increasing Risk:**
  - `loan_int_rate = 15.55`
  - `loan_grade = 3`
  - `loan_log_income_ratio = 0.13`
  - `person_income = 132000.0`
- **🔵 Features Decreasing Risk:**
  - `loan_intent = 5.0`
  - `person_emp_length = 6.0`
- **Narrative:**  
  High interest rate and low loan grade are major risk drivers. Although the applicant has long employment and a neutral loan intent, the model still leans toward a moderately high-risk prediction.

---

## Case 3:High-Risk borderline Applicant
- **Base Value:** `0.0`  
- **Model Output:** `1.47`  
- **🔴 Features Increasing Risk:**
  - `person_age = 23.0`
  - `loan_intent = 3.0`
  - `person_home_ownership = 3.0`
  - `loan_to_income_ratio = 0.33`
  - `loan_grade = 1.0`
- **🔵 Features Decreasing Risk:**
  - `loan_percent_income = 0.28`
  - `person_income = 61200.0`
- **Narrative:**  
  This is a borderline case. Young age and loan characteristics push risk up, but decent income and loan percent help balance it. The model output is modestly above the base value.
---

## Case 4: Low-Risk Applicant
-**Base Value:** `~0.0`  
- **Model Output:** `-1.37`  
- **🔴 Features Increasing Risk:**
  - `cb_person_home_ownership = 0.0`
  - `loan_intent = 3.0`
  - `cb_person_default_on_file`
  - `person_income_rate = -0.10`
- **🔵 Features Decreasing Risk:**
  - `loan_grade_A`
  - `person_income = 57100.0`
  - `person_age = 21.0`
  - `loan_int_rate = 13.48`
- **Narrative:**  
  This applicant is predicted as low risk. Strong loan grade and income reduce risk, while default history and home ownership status add some upward pressure. The model ultimately favors a safe outcome.
---

## Case 5: Low-Risk Applicant
- **Base Value:** `~0.0`  
- **Model Output:** `-1.80`  
- **🔴 Features Increasing Risk:**
  - `loan_int_rate = 11.2`
  - `person_home_ownership = 0.0`
  - `person_income = 34500.0`
- **🔵 Features Decreasing Risk:**
  - `loan_grade = 1.0`
  - `loan_percent_income = 0.26`
  - `person_age = 28`
  - `loan_emp_length = 5.0`
- **Narrative:**  
  Despite moderate income and interest rate, the model predicts low risk due to strong loan grade, age, and employment length. This case is seen as financially stable.

## Force plots for risk samples
- `plots/7.False positive plot.png`
- `plots/8.true negative plot.png`
- `plots/9.Borderline case plot.png`
- `plots/10.Highrisk  plot.png`
- `plots/11.low risk plot.png`
---
