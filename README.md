#  🚨 Prototype Early Warning System combining NEWS2/qSOFA rule-based scoring with a machine-learning deterioration-risk model

In this ML project, I explored whether routinely collected clinical variables could be transformed into an interpretable deterioration-risk tool suitable for resource-constrained clinical environments. It uses retrospective clinical data such as diagnosis, demographics, comorbidities, vital sign combined with NEWS2 and QSOFA score to support evidence-based approach. 

## 📌 Objectives
- Identify patients groups at high risk of clinical deterioration

- Develop early warning score system for timely intervention and early consultation

- Assess feasibility for daily implementation into routine clinical workflow

- Develop simple desktop based app for offline deployment in resource constrained setting 

- Propose scaling up strategies to multicentered study application 
## 📊 Dataset
Data source: Deidentified patient EMR registery hospital medical ward 

Entry criteria: 

- All adult > 18 yrs, admitted to medical ward from July 1, 2025 to July 31, 2026

- Vital sign record at least 80% availability

Exclusion Criteria: Missing reports >20%, Direct ICU transfer from ER, Referred from other facility

Variables: Main diagnosis (Penmonia), Comborbidities (Heart failure, Asthma/COPD, , Acute Kidney disease, Anemia)
## 🔬 Methods

### 1. Data Preprocessing

Handling missing values and normalization, imputed when <20%.
Feature encoding for categorical variables.
### 2. Exploratory Data Analysis (EDA)

Missing values , Sex distribution, Age distribution, Shock Index , Deteriorated
### 3. Modeling
#### News2 and QSOFA scoring engine implementation
#### Define subgroups (Anemia, HF, HIV, Age)
#### Feature engineering

- X: features (vital sign, diagnosis, comorbidity, age)

- Y: Detriorated in 48 hours

 #### Model performance 

- Deterioration rate subgroup comparison

- Model comparison: News2 alone Vs ML

- Time to deterioration by subgroup
  
### 4. Model Training

- Null values imputed

- Train/test split to avoid overfitting. Hyperparameter tuning.

- Model 1: Logistic regression

- Model 2: Gradiant Boost

- Shap plot cross model 

Flask web app development to test model performance on prospective dataset 

## 📈 Key Results

### Exploratory Data anlysis

Missing values: ranged from 10-20, and admission heart rate and 24 heart rate recording highest 20 missing values, followed by 24 respiratory rate at 18 and admission temperature at 13.
  
Sex distribution: 

- Male: 685

- Female: 555

Age distribution:

- <30: 130
  
- 30-50: 393
  
- 51-70: 384 and >71: 333

### Subgroup Analysis: Performance varied across different patient subgroups:

Pneumonia Only (no HF):

- Patients: 201, Deterioration Rate: 15.4%

- AUC: 0.791

Pneumonia + Heart Failure:

- Patients: 171, Deterioration Rate: 35.7%

- AUC: 0.815

Pneumonia + HF + Anemia:

- Patients: 92, Deterioration Rate: 39.1%

- AUC: 0.802

HIV Positive:

- Patients: 19, Deterioration Rate: 10.5%

- AUC: 0.971

Age > 60:

- Patients: 157, Deterioration Rate: 24.8%

- AUC: 0.726
  
### Model Comparison (ML Model vs. NEWS2 Alone):

NEWS2 Alone AUC (Test Set): 0.845
ML Model AUC (Test Set - GB): 0.820
Improvement: -0.025 (+-3.0%) -- vs NEWS2

### Overall Model AUC: 
The machine learning model achieved an AUC of (Test Set) 0.820.

### Time to Deterioration by Subgroup: 

Pneumonia Only (no HF): Mean 31 hours from admission

Pneumonia + Heart Failure: Mean 30 hours from admission

Pneumonia + HF + Anemia: Mean 30 hours from admission

HIV: Mean 

Age > 60: Mean 31 hours from admission

## Limitation
- Small sample size

- missing data

- generalizability needs further population group studies
## 🧩 Clinical Relevance
- Address daily challange and gap in patient risk stratefication

- Generate evidence to support early intervention in patients at high risk to optimize care and improve clnical outcome

## Future Direction

- Asses with increased sample size, increased features (IV fluids, Drugs including iontrops, LAB Values such as: creatinine, serum electrolyte when available, ECHO,clinicians notes for treatment recommendations and guidance)

- Multicentered implemnetation to assess replicabality of the model

- Implement in emergency setup with refined parameters and close time observation where clinical significance have more robust outcome 
## 🚀 How to Run

Requirements

Python 3.x

pandas, numpy, matplotlib, seaborn

scikit-learn

Data source: available upon request 

## Author

Yonatan Yotora, MD

Adare General Hospital ,Hawassa, Ethiopia
