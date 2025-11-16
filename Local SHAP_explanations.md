# Descriptions of local SHAP explanations

##  Local SHAP Analysis for 5 Loan Applications
- Select **3 high-risk** and **2 low-risk** samples

## SHAP Dependence Plot
- `plots/5.SHAP Dependance plot.png`

## Force plots for risk samples
- `plots/6.Force plot for global fearures.png`

---

## Local SHAP Explanations: Force Plot Narratives

## Case 1: High-Risk Applicant
- **Base Value:** `0.0`  
- **Model Output:** `6.63`  
-  ** Features Increasing Risk:**
  - `person_home_ownership = 3.0`(likely indicates a less stable or riskier ownership type, e.g., "other" or "rent")
  - `loan_percent_income = 0.83`(very high loan burden relative to income)
  
-  ** Moderately Increasing Risk:**
  - `person_income = 130000.0`(counterintuitively increases risk—possibly due to correlation with larger loans)
  - `loan_to_income_ratio = 0.13`(adds to perceived repayment strain)
- ** Features Decreasing Risk:**
  - `loan_grade = 0.0`(likely a top-tier grade, mitigating risk)
- **Narrative:**  
  Although the applicant earns a high income, the model flags them as high risk due to a disproportionately large loan relative to income and a potentially unstable home ownership status. The favorable loan grade helps slightly, but the overall risk remains elevated due to the heavy financial burden.
---

## Case 2: High-Risk Applicant
- **Base Value:** `0.0`  
- **Model Output:** `3.29`  
- ** Features Increasing Risk:**
  - `loan_int_rate = 15.55`(very high interest rate signals lender concern)
  - `loan_grade = 3`(mid-to-low grade, indicating weaker creditworthiness)
- ** Mildly Increasing Risk:**
  - `loan_log_income_ratio = 0.13`(suggests income may not scale well with loan size)
  - `person_income = 132000.0`(again, high income not protective—possibly due to associated loan size)
- ** Decreasing Risk:**
  - `loan_intent = 5.0`(possibly a low-risk purpose like education or home improvement)
  - `person_emp_length = 6.0` (moderate employment stability)
- **Narrative:**  
  The model identifies this applicant as high risk primarily due to the steep interest rate and a suboptimal loan grade. While employment history and loan purpose help reduce risk, they are outweighed by financial indicators suggesting potential repayment difficulty.
---
## Case 3:High-Risk borderline Applicant
- **Base Value:** `0.0`  
- **Model Output:** `1.47`  
- ** Features Increasing Risk:**
  - `person_age = 23.0`(young age may imply limited credit history)
  - `loan_intent = 3.0`(possibly a riskier loan purpose like personal use)
  - `person_home_ownership = 3.0`(less secure housing status)
  - `loan_to_income_ratio = 0.33`(moderate loan burden)
  - `loan_grade = 1.0`(slightly below top grade)
- ** Decreasing Risk:**
  - `loan_percent_income = 0.28`(manageable loan size relative to income)
  - `person_income = 61200.0`(moderate income helps offset risk)
- **Narrative:**  
  This applicant sits near the risk threshold. Youth and loan characteristics raise concerns, but a reasonable income and loan size help balance the profile. The model leans slightly toward risk, but not decisively.
---
## Case 4: Low-Risk Applicant
-**Base Value:** `~0.0`  
- **Model Output:** `-1.37`  
- ** Features Increasing Risk:**
  - `cb_person_home_ownership = 0.0`(possibly no ownership or unstable housing)
  - `loan_intent = 3.0` (potentially discretionary spending)
  - `cb_person_default_on_file`(past default is a red flag)
  - `person_income_rate = -0.10`(negative growth or low income relative to peers)
- ** Features Decreasing Risk:**
  - `loan_grade_A`(top-tier creditworthiness)
  - `person_income = 57100.0`(stable income)
  - `person_age = 21.0`(young but not extremely so)
  - `loan_int_rate = 13.48`(moderate interest rate)
- **Narrative:**  
  This applicant is predicted as low risk. Despite a few risk signals—like a past default and uncertain home ownership—the applicant benefits from a strong loan grade and steady income. These positive indicators dominate, leading the model to a low-risk prediction.
---
## Case 5: Low-Risk Applicant
- **Base Value:** `~0.0`  
- **Model Output:** `-1.80`  
- ** Features Increasing Risk:**
  - `loan_int_rate = 11.2`(moderate interest rate)
  - `person_home_ownership = 0.0`(possibly renting or no ownership)
  - `person_income = 34500.0`(lower income bracket)
- ** Features Decreasing Risk:**
  - `loan_grade = 1.0`(good credit grade)
  - `loan_percent_income = 0.26`(low loan burden)
  - `person_age = 28`(mature borrower)
  - `loan_emp_length = 5.0`(solid employment history)
- **Narrative:**  
  Although the applicant has a modest income and lacks home ownership, the model sees them as low risk due to a favorable loan grade, low loan burden, and stable employment. These factors collectively outweigh the moderate risk contributors.
## Force plots for risk samples
- `plots/7.High risk 1 plot.png`
- `plots/8.Highrisk 2 plot.png`
- `plots/9.High risk Borderline case plot.png`
- `plots/10.Low risk 1 plot.png`
- `plots/11.low risk2 plot.png`
---
