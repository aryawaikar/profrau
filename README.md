# 💊 Prescription Fraud Detection – Data Analytics & Preprocessing Project

This project performs full data exploration, preprocessing, aggregation, fraud trend analysis, statistical analysis, visualization, and feature engineering on a medical prescription dataset. The goal is to prepare the data so that fraud-prediction ML models can be built later.

---

## 🎯 Project Purpose

- Understand dataset and detect suspicious patterns
- Clean and transform raw data (text → numeric)
- Check missing values and statistical trends
- Identify fraud frequency per month
- Prepare final dataset for ML (scaled + encoded)
- Visualize cost behavior and anomalies

---

## 📂 Dataset Overview

Dataset Shape: 500 rows × 25 columns  
Source Notebook: **projectp2 – Jupyter Notebook** 

### 📌 Sample Raw Dataset Output (first 5 rows)

Prescription_ID | Patient_ID | Doctor_ID | Pharmacy_ID | Drug_Name | Drug_Category | Dosage | Prescription_Date | Refill_Count | Insurance_Claim
--------------- | ---------- | ---------- | ----------- | -------- | ------------- | ------ | ----------------- | ------------ | ----------------
1 | 9107 | 103 | 678 | Insulin | Antibiotic | 98mg | 2024-06-07 | 4 | 0
2 | 3997 | 917 | 253 | Hydrocodone | Antibiotic | 26mg | 2024-02-04 | 1 | 0
3 | 7561 | 896 | 623 | Metformin | Hypertension | 471mg | 2024-03-15 | 0 | 1
4 | 1509 | 704 | 998 | Lisinopril | Hypertension | 342mg | 2024-02-06 | 5 | 1
5 | 1804 | 853 | 551 | Oxycodone | Antibiotic | 180mg | 2024-01-11 | 5 | 1

---

## 🧹 Data Preprocessing Summary

Performed inside notebook 

- Dosage text like “98mg” converted → numeric (98)
- Missing values checked → dataset had **0 missing entries**
- Numerical values (Cost, Age, Dosage, Days_Supply) transformed using scaling
- Categorical columns encoded into multiple numeric dummy columns
- Final transformed dataset contained **132 columns**

---

## 📈 Monthly Fraud Trend (Direct Notebook Output)

Month | Fraudulent Claims
------|------------------
2024-01 | 30
2024-02 | 23
2024-03 | 21
2024-04 | 23
2024-05 | 19
2024-06 | 16
2024-07 | 21
2024-08 | 18
2024-09 | 23
2024-10 | 19
2024-11 | 24
2024-12 | 25

📌 Interpretation: Fraud is highest in **January, November, December** → seasonal pattern of insurance misuse

---

## 📐 Statistical Analysis (As Displayed in Notebook)

Mean of Total Cost: 513.82604  
Median of Total Cost: 510.445  
Mode of Total Cost: 164.62  
IQR (Interquartile Range): 466.5450000000001  
Variance: 78333.47627566973  
Standard Deviation: 279.88118242509574  
Coefficient of Variation (CV): 54.47%  
Mean Absolute Deviation (MAD): 241.07819247999996  

### Markdown Table Version

Metric | Value
------ | -----
Mean | 513.83
Median | 510.44
Mode | 164.62
IQR | 466.54
Variance | 78,333.47
Standard Deviation | 279.88
Coefficient of Variation | 54.47%
Mean Absolute Deviation | 241.08

---

## 📊 Doctor-Level Prescription Summary

Doctor_ID | Total_Cost | Prescription_Count | Fraudulent_Claim_Count
--------- | ---------- | ------------------ | ----------------------
101 | 1022.84 | 2 | 0
105 | 1725.94 | 2 | 1
106 | 235.62 | 1 | 1
110 | 389.34 | 1 | 0

---

## 🎨 Visualizations Performed

- Box Plot of Total Cost → detects extreme billings (possible fraud)
- Histogram of Total Cost → cost distribution shape
- Monthly fraud graph

---

## 🧠 Final Dataset Result

After preprocessing:

- Original Columns: 25
- Final Columns (Encoded): **132**
- Dataset is now **fully numeric**
- Ready for ML classification model training

---

## 🚀 Suggested Next Steps

Task | Reason
---- | ------
Train ML Model (RandomForest / Logistic Regression / XGBoost) | Predict fraud
Evaluate Accuracy, Precision, Recall, ROC-AUC | Validate performance
Save trained model using joblib | Deployment use
Deploy REST API (FastAPI / Flask) | Real-time fraud check
Streamlit dashboard | Visualization for pharma companies

---

## 👤 Author

Prescription Fraud Detection – Academic Data Analytics  
Python | Pandas | NumPy | Seaborn | scikit-learn

