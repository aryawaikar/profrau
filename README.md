# 💊🏥 Healthcare Prescription Dataset – Analytics, Preprocessing & ML Classification

This project analyzes a medical prescription dataset, detects suspicious patterns, performs preprocessing and statistical analysis, and applies machine-learning for predictive insights.  
The dataset includes hospital-wide prescription activity, patient demographics, doctor information, medication types, costs and a fraud-risk label.

---

## 🎯 Objective

- Understand and analyze healthcare prescription data
- Detect fraud-risk patterns in medical billing and prescriptions
- Clean & preprocess raw data (text → numeric, scaling, encoding)
- Perform statistical analysis on Total Cost and identify anomalies
- Study seasonal/monthly variations in fraudulent claims
- Train machine-learning models to predict healthcare performance outcomes

---

## 📂 Dataset Overview

Dataset Shape: **500 rows × 25 columns**

### 📌 Sample Dataset Output (first 5 rows)

Prescription_ID | Patient_ID | Doctor_ID | Pharmacy_ID | Drug_Name | Drug_Category | Dosage | Prescription_Date | Refill_Count | Insurance_Claim
--------------- | ---------- | ---------- | ----------- | -------- | ------------- | ------ | ----------------- | ------------ | ----------------
1 | 9107 | 103 | 678 | Insulin | Antibiotic | 98mg | 2024-06-07 | 4 | 0
2 | 3997 | 917 | 253 | Hydrocodone | Antibiotic | 26mg | 2024-02-04 | 1 | 0
3 | 7561 | 896 | 623 | Metformin | Hypertension | 471mg | 2024-03-15 | 0 | 1
4 | 1509 | 704 | 998 | Lisinopril | Hypertension | 342mg | 2024-02-06 | 5 | 1
5 | 1804 | 853 | 551 | Oxycodone | Antibiotic | 180mg | 2024-01-11 | 5 | 1

### Key Columns

- Patient & Doctor info
- Drug name, category, dosage
- Insurance claim flag
- Total cost
- Health condition, demographics
- Fraudulent Claim (target)
- Refill count & duration

---

## 🧹 Data Preprocessing Summary

Actions performed:

- Converted `"98mg"` → **98**
- Checked missing values → **none found**
- Encoded categorical columns → Drug_Name, Doctor_Specialty, Patient_Health_Condition, Pharmacy_Location
- Scaled numeric columns → Total_Cost, Age, Dosage, Days_Supply
- Final processed dataset: **132 columns (from 25)** → ML-ready

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

📌 Insight → Fraud is highest in **January, November & December**, indicating seasonal exploitation.

---

## 📐 Statistical Analysis – Total Cost

Mean: 513.83  
Median: 510.44  
Mode: 164.62  
IQR: 466.54  
Variance: 78,333.47  
Standard Deviation: 279.88  
Coefficient of Variation: 54.47%  
MAD: 241.08  

### Tabular Summary

Metric | Value
------ | -----
Mean | 513.83
Median | 510.44
Mode | 164.62
IQR | 466.54
Variance | 78,333.47
St. Dev | 279.88
CV | 54.47%
MAD | 241.08

---

## 👨‍⚕️ Doctor-Level Suspicion Summary

Doctor_ID | Total Cost | Prescription Count | Fraud Count
----------|------------|-------------------|-------------
101 | 1022.84 | 2 | 0
105 | 1725.94 | 2 | 1
106 | 235.62 | 1 | 1
110 | 389.34 | 1 | 0

🩺 Doctors with **high count + high fraud claims** become red-flag indicators.

---

## 🤖 Machine-Learning Classification

Random Forest models were trained to analyze prescription-based hospital outcome performance categories.

### Performance Summary

Outcome Metric | Accuracy | F1-Score
-------------- | -------- | --------
Safety of care | 0.733 | 0.733
Patient experience | 0.722 | 0.723
Readmission | 0.718 | 0.729
Efficient use of imaging | 0.653 | 0.682
Mortality | 0.631 | 0.671
Timeliness of care | 0.603 | 0.584
Effectiveness of care | 0.572 | 0.654

✔ Acceptable ≥ 0.70  
⚠ Below 0.65 → suggests dataset imbalance & missing contextual hospital performance data

---

## 🧠 Outputs Generated

- Cleaned & encoded dataset (CSV export)
- Fraud-trend tables & summaries
- Statistical summary for Total Cost
- Visualizations  
  - Box Plot (cost)  
  - Histogram (cost distribution)  
  - Monthly fraud line chart  
- ML models saved (.joblib)
- Accuracy reports for hospital metrics

---

## 🚀 Possible Enhancements

Add | Benefit
----|--------
Fraud-prediction ML model (classification) | Automate anomaly detection
Deploy via Flask / FastAPI | Real-time fraud detection API
Streamlit dashboard | Visual analytics tool
Add doctor-risk scoring | Rank doctors by suspicious activity

---

## 👤 Author

Healthcare Prescription Data Analytics & ML  
Tools: Python, Pandas, NumPy, Matplotlib, Scikit-Learn, Seaborn


