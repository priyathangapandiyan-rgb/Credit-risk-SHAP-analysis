 # Strategic Summary: Top 3 Drivers of Credit Risk via SHAP Analysis

### Feature Importance Comparison

## XGBoost Gain Importance
- XGBoost’s built-in metrics are useful for quick feature ranking but may miss deeper patterns.

## SHAP Importance
- SHAP provides richer interpretability, showing both magnitude and direction of feature influence.

## Differences Observed
- For policy decisions and fairness audits, SHAP is the preferred method for understanding model behavior.

---

This summary highlights the most influential features driving credit risk predictions, based on SHAP interpretability and model importance metrics.

---

## 1. **Applicant Income (`person_income`)**
- **SHAP Insight:**  
  Low income consistently increases predicted risk across individual cases. SHAP values show strong negative contributions for low-income applicants, while higher income sometimes interacts with other features to increase risk.
- **Dependence Plot Insight:**  
  SHAP values rise sharply with income, but the effect is **modulated by loan grade** — high-income applicants with poor loan grades still show elevated risk.
- **Model Importance:**  
  Ranked #2 in SHAP summary plot and #1 in XGBoost feature importance.
- **Policy Implication:**  
  - Segment applicants by income bands for tailored risk assessment.  
  - Offer income-adjusted repayment plans and financial literacy programs.  
  - Monitor income-to-loan grade interactions to detect hidden risk among high earners.
---

## 2. **Loan Intent (`loan_intent`)**
- **SHAP Insight:** Personal and education loans show higher risk (positive SHAP values).
- **Model Importance:** Ranked #4 in SHAP summary plot and Ranked #2 in XGBoost (importance score: 174.0).
- **Policy Implication:**
  - Apply differentiated underwriting based on loan purpose.
  - Require stricter documentation for high-risk intents.
  - Consider risk-sharing schemes for education loans.

---

## 3. **Loan Grade (`loan_grade`)**
- **SHAP Insight:**  
  Lower grades (e.g., Grade 1 or 3) consistently push predictions higher, indicating elevated risk. Higher grades reduce predicted risk.
- **Dependence Plot Insight:**  
  Loan grade interacts with income — even high-income applicants show risk if their loan grade is poor.
- **Model Importance:**  
  Ranked #1 in SHAP summary plot and #3 in XGBoost importance.
- **Policy Implication:**  
  - Use loan grade as a composite risk signal for pricing and approval thresholds.  
  - Align internal grading systems with SHAP-driven insights for transparency.  
  - Promote responsible lending by incentivizing higher-grade applications.
---

##  Supporting Evidence
- **SHAP Summary Plot:**  
  Confirms wide SHAP value ranges and strong directional influence for top features.
- **Force Plots:**  
  Show consistent patterns across individual cases, especially the push from low income and risky loan intents.
- **Dependence Plot (`person_income` vs. SHAP value):**  
  Reveals nonlinear effects and interactions with loan grade.
- **XGBoost Importance Chart:**  
  Validates these features as top contributors to model decisions.

## 9. Conclusion
This interpretable ML framework successfully identifies key drivers of credit risk and provides actionable insights using SHAP.  
The project ensures transparency, model reliability, and compliance with explainability requirements.

---


  
