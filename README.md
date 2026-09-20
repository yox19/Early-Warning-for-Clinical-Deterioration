#  🚨 Prototype Early Warning System combining NEWS2/qSOFA rule-based scoring with a machine-learning deterioration-risk model

In this ML project, I explored whether routinely collected clinical variables could be transformed into an interpretable deterioration-risk tool suitable for resource-constrained clinical environments. It uses retrospective clinical data such as diagnosis, demographics, comorbidities, vital sign combined with NEWS2 and QSOFA score to support evidence-based approach. 

## 📌 Objectives
- Identify high risk groups for clinical derioration

- validate applicabilty for timely intervention and early consultation

- Assess feasibility for daily implementation into routine clinical workflow

- Develop simple desktop based app for offline deployment in resource constrained setting 

- Propose scaling up strategies to multicentered study application 
## 📊 Dataset
Data source: Deidentified patient EMR registery hospital medical ward 

Entry criteria: 

- All adult > 18 yrs, admitted to medical ward from July 1, 2025 to July 31, 2026

- Vital sign record at least 80% availability

Exclusion Criteria: Missing reports >20%, Direct ICU transfer from ER, Referred from other facility

Variables: Main diagnosis ( Penmonia), Comborbidities (Heart failure, Asthma&COPD, Hypertension, Kidney disease, Previous Stroke)
## 🔬 Methods

### 1. Data Preprocessing

Handling missing values and normalization, imputed when <20%.
Feature encoding for categorical variables.
### 2. Exploratory Data Analysis (EDA)

Missing values , Sex distribution, Age distribution, Shock Index , Improved, Death, DAMA
### 3. Modeling
#### News2 and QSOFA scoring engine implementation

#### Defined subgroups (Anemia, HF, Pnemonia, HIV)

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

Missing values: ranged from 10-20, and admission HR and 24 HR recording highest 20 missing values, followed by 24 RR at 18 and admission temp at 13.
  
Sex distribution: 

- Male: 274

- Female: 226

Age distribution:

- <30: 1
  
- 30-50: 68
  
- 51-70: 137 and >71: 294

### Subgroup Analysis: Performance varied across different patient subgroups:

- Pneumonia Only (no HF): AUC of 0.939
  
- Pneumonia + Heart Failure: AUC of 0.881
  
- Pneumonia + HF + Anemia: AUC of 0.809
  
- HIV Positive: AUC of 0.894
  
- Age > 60: AUC of 0.911
  
### Model Comparison (ML Model vs. NEWS2 Alone):

- NEWS2 Alone AUC: 0.898
  
- ML Model AUC: 0.920
  
The ML model showed an improvement of 0.021 AUC (+2.4%) over NEWS2 alone.

### Overall Model AUC: 
The machine learning model achieved an AUC of 0.920, indicating strong overall performance in predicting deterioration.

### Time to Deterioration by Subgroup: 
The mean time to deterioration across subgroups ranged from 30 to 32 hours from admission.

## Limitation
- Small sample size

- missing data

- generalizability needs further population groups studies
## 🧩 Clinical Relevance
- Adreess daily challange and gap in patient risk stratefication

- Generate evidence to support early intervention in patients at high risk to optimize care and improve clnical outcome

## Future Direction

- Asses with increased sample size, increased features (IV fluids, Drugs including iontrops)LAB Values such as: creatinine, serum electrolyte when available, ECHO,clinicians notes for treatment recommendations and guidance)

- Multicentered implemnetation to assess replicabality of the model

- Implement in emergency setup with refined parameters and close time observation where clinical significance will more value 
## 🚀 How to Run

Requirements

Python 3.x

pandas, numpy, matplotlib, seaborn

scikit-learn

## Author

Yonatan Yotora, MD

Adare General Hospital ,Hawassa, Ethiopia
