# Predicting Risk of Acute Kidney Injury (AKI) from Nephrotoxic Drugs in ICU Patients Using MIMIC-IV

## Overview

This project develops and evaluates machine learning models to predict the risk of Acute Kidney Injury (AKI) in ICU patients following exposure to nephrotoxic medications. Leveraging the MIMIC-IV database, the study integrates patient demographics, drug exposure, vitals, and lab values to support early identification and intervention for high-risk patients.

---

## Type of Analysis

**Predictive Modeling and Explainable AI**

- Supervised classification using multiple machine learning models
- Feature engineering from ICU drug administration, labs, and comorbidities
- SHAP-based model interpretation and feature importance analysis
- Threshold tuning for sensitivity/precision optimization

---

## Objectives

- Identify top predictors of AKI in critically ill patients exposed to nephrotoxic drugs  
- Build and evaluate multiple models for AKI risk prediction  
- Use explainability techniques (SHAP) to support model trustworthiness  
- Compare model performance under fixed and optimized thresholds

---

## Dataset

- **Source**: MIMIC-IV v3.1  
- **Population**: Adult ICU patients receiving nephrotoxic drugs  
- **Outcome**: AKI (based on KDIGO criteria, lab thresholds)  
- **Features**:
  - Drug exposure (type, dosage, timing)
  - Creatinine, BUN, Urine Output, Electrolytes
  - Vitals and comorbidity indicators

---

## Methodology

- SQL extraction and cohort definition in PostgreSQL  
- Feature engineering across time windows relative to drug exposure  
- Model training using:
  - Logistic Regression
  - Random Forest
  - XGBoost
  - LightGBM
  - Gradient Boosting (GBM)
- Performance tuning and evaluation using:
  - AUC, Accuracy, F1 Score
  - Sensitivity, Precision, Specificity
  - Fixed and optimized thresholds per model

---

## Key Results

### Evaluation at Fixed Threshold (0.05)

| Model     | Sensitivity | Precision | AUC   |
|-----------|-------------|-----------|--------|
| GBM       | 1.000       | 0.280     | 0.730  |
| LGBM      | 0.999       | 0.281     | 0.729  |
| XGB       | 0.998       | 0.281     | 0.729  |
| RF        | 1.000       | 0.279     | 0.725  |
| LogReg    | 1.000       | 0.279     | 0.699  |

### Evaluation at Optimal Thresholds

| Model     | Threshold | Sensitivity | Precision | AUC   | F1 Score | Specificity |
|-----------|-----------|-------------|-----------|--------|----------|--------------|
| GBM       | 0.25      | 0.699       | 0.432     | 0.730  | 0.382    | 0.925        |
| LGBM      | 0.30      | 0.610       | 0.463     | 0.729  | 0.394    | 0.921        |
| XGB       | 0.29      | 0.630       | 0.457     | 0.729  | 0.378    | 0.924        |
| RF        | 0.31      | 0.600       | 0.469     | 0.725  | 0.282    | 0.959        |
| LogReg    | 0.28      | 0.597       | 0.453     | 0.699  | 0.333    | 0.935        |

---

## Interpretability

- Used SHAP values to rank features by their contribution to AKI risk  
- Top predictors included:
  - Elevated creatinine and BUN  
  - Specific nephrotoxic drugs (e.g., aminoglycosides, NSAIDs)  
  - Baseline vitals and urine output

---

## Tools & Technologies

- Python, Jupyter  
- PostgreSQL (MIMIC-IV)  
- Scikit-learn, XGBoost, LightGBM  
- SHAP, Matplotlib, Seaborn  

---

## Skills Demonstrated

- Clinical machine learning using real-world ICU data (MIMIC-IV)
- Predictive modeling and model evaluation (AUC, precision, sensitivity, F1)
- Threshold tuning for sensitivity-specificity tradeoffs
- Cohort construction and clinical feature engineering
- Explainable AI (XAI) using SHAP for model interpretability
- Risk stratification for adverse drug outcomes
- Health informatics and ICU decision support
- SQL-based data extraction from EHR databases
- Evidence-based AI implementation in clinical research

---

## Author

**Alanoud Alturki**  
Health Data Analyst | Health Informatics Specialist | Pharmacist  
MS in Health Informatics · MS in Health Data Analysis · PhD Student  
[LinkedIn](https://www.linkedin.com/in/alanoud-alturki-5601b2b5)

---

## License

This project is for research use only. Data source: MIMIC-IV (de-identified, publicly available). 
