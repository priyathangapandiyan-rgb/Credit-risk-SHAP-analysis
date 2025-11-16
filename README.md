# **Credit Risk Analysis, Prediction & Explainability**
🚀 A machine learning project for predicting credit risk with interpretability and explainability using SHAP analysis.
---

## **📌 Project Overview**

This project builds a credit risk prediction model using machine learning to classify loan applicants as defaulters or non-defaulters. The model is interpreted using SHAP to explain predictions.And explain the drivers of credit risk, these findings in terms of potential policy adjustments for a lending institutions.
---
##📂 **Repository Structure**

```
credit-default-shap-project/
│
├── project.ipynb
├── report.md
├── requirements.txt
├── default_credit.xls (or data file)
│
└── plots/
    ├── 1.Correlation matrix of features.png
    ├── 2.Global SHAP Plot.png
    ├── 3.Global features summary SHAP Plot.png
    ├── 4.Feature importance plot.png
    └── 5.SHAP Dependance plot.png
    ├── 6.Force plot for global fearures
    ├── 7.False positive plot
    ├── 8.true negative plot
    ├── 9.Borderline case plot
    ├── 10.Highrisk  plot
    ├── 11.low risk plot
```

---

## **📂 Dataset**
The dataset contains loan applicant information with features such as:
- **Personal details** (Age, Income, Employment Length)
- **Loan details** (Amount, Interest Rate, Grade, Intent)
- **Credit history** (Default on File, Credit History Length)
- **Credit history** (Default on File, Credit History Length) Loan status (0 = No Default, 1 = Default)

📌 **Dataset Source**: Public credit risk datasets from **Kaggle / Lending Club / Home Credit**.
---

## **🔍 Data Analysis**
We conducted **exploratory data analysis (EDA)** to understand the dataset structure and detect any inconsistencies.

### **✔ Steps in Data Analysis**
1. **Missing Value Handling**
- Filled missing values for `person_emp_length` with **median**.
- Replaced missing values for `loan_int_rate with` **mean**.

2. **Outlier Removal**
- Removed **age > 80** (unrealistic for loan applicants).
- Removed **employment length > 60** (not practical).

3. **Feature Engineering**
- **Loan-to-Income Ratio** = `loan_amnt / person_income`
- **Loan-to-Employment Length Ratio** = `person_emp_length / loan_amnt`
- **Interest Rate-to-Loan Ratio** = `loan_int_rate / loan_amnt`

4. **Class Imbalance Handling**
- Applied SMOTE (Synthetic Minority Oversampling Technique) to balance default & non-default cases.
---

## **🧪 Model Training**
To ensure **robust performance** , we trained model and analysis it.

### **✔ Models Used**
- **XGBoost**
- **Random Forest**

### Evaluation Metrics
- **AUC Score**
- **F1 Score**
- **Precision**
- **Recall**
---
## 🔍 Interpretability
This project uses **SHAP** for:

### ✔ Global Interpretability
- Top 10 most important features
- SHAP Summary plot
- Feature importance SHAP plot

### ✔ Local Interpretability
- False Negative case
- True Positive case
- Borderline correct prediction
- Five credit risk applicants
----
## 🛠 How to Run the Project

### Option 1 — Google Colab (Recommended)
1. Upload the dataset and notebook  
2. Install packages using `requirements.txt`  
3. Run cells from top to bottom  

### Option 2 — Local Machine
```
pip install -r requirements.txt
jupyter notebook project.ipynb
```

---

## 🧠 Key Insights
- **Loan-to-Income Ratio** is the most significant factor in predicting default risk.  
- **Longer credit history** reduces the probability of default.  
- **Higher interest rates** increase the risk of default.  
- **Loan intent (purpose of the loan)** plays a crucial role in classification.  

---

Local explanations highlight model errors and risk patterns.


