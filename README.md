#  🚨 Prototype Early Warning System combining NEWS2/qSOFA rule-based scoring with a machine-learning deterioration-risk model

In this ML project, I explored whether routinely collected clinical variables could be transformed into an interpretable deterioration-risk tool suitable for resource-constrained clinical environments. It uses retrospective clinical data such as diagnosis, demographics, comorbidities, vital sign combined with NEWS2 and QSOFA score to support evidence-based approach. 

## 📌 Objectives

## 📊 Dataset

## 🔬 Methods

### 1. Data Preprocessing

Handling missing values and normalization.
Feature encoding for categorical variables.
### 2. Exploratory Data Analysis (EDA)

Missing values , Sex distribution, Age distribution
### 3. Modeling

Logistic Regression

ROC-AUC
### 4. Model Refinement

Train/test split to avoid overfitting.
Hyperparameter tuning.
Comparison of performance across models.

## 📈 Key Results

### Exploratory Data anlysis

Missing values: ranged from 20-10, and admission HR and 24 HR recording highest 20 missing values, followed by 24 RR at 18 and admission temp at 13.
  
Sex distribution: 

- Male: 274

- Female: 226

Age distribution:

- <30: 1
  
- 30-50: 68
  
- 51-70: 137
  
- >70: 294
  
### Overall Model AUC: 
The machine learning model achieved an AUC of 0.920, indicating strong overall performance in predicting deterioration.

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

### Time to Deterioration by Subgroup: 
The mean time to deterioration across subgroups ranged from 30 to 32 hours from admission.

## Limitation

## 🧩 Clinical Relevance

## 🚀 How to Run

Requirements

Python 3.x

pandas, numpy, matplotlib, seaborn

scikit-learn

## Author

Yonatan Yotora, MD

Adare General Hospital ,Hawassa, Ethiopia
