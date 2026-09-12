# Early Risk Detection for Student Success — OULAD

An early-warning machine learning project using the Open University Learning Analytics Dataset (OULAD) to identify students at risk of failing or withdrawing.

[![Report](https://img.shields.io/badge/📄_Stakeholder_Report-PDF-1E2A4A?style=for-the-badge)](reports/report_vfinal.pdf)

A concise, non-technical summary of the full analysis — key results, early-warning timing, and advisor recommendations in 9 pages.

## Objective

The project aims to:

- Identify at-risk students early enough for advisors to intervene.
- Understand the factors associated with student risk.
- Explain individual model predictions.
- Identify useful early-warning checkpoints.
- Translate model findings into practical advising recommendations.

## Dataset

The project uses the Open University Learning Analytics Dataset (OULAD), combining:

- Student demographic information
- Registration information
- Assessment results
- Course information
- Virtual Learning Environment (VLE) activity

## Pipeline

Business Problem  
→ Data Understanding  
→ Data Cleaning  
→ Feature Engineering  
→ Exploratory Data Analysis  
→ Baseline vs Ensemble Modeling  
→ Interpretability  
→ Early Warning Timing  
→ Stakeholder Recommendations

## Modeling

The primary modeling task is binary early-risk detection:

- **At Risk:** Fail or Withdrawn
- **Not At Risk:** Pass or Distinction

A Logistic Regression model was used as the simpler baseline and Random Forest as the ensemble model.

## Key Results

- Random Forest Average Precision: **0.8716**
- Random Forest ROC-AUC: **0.8358**
- Meaningful risk signal was detectable by **Day 7**
- Model performance improved from Day 7 through Day 28
- Students with no early VLE activity had a **95.7% at-risk rate**
- The strongest global feature by permutation importance was **code_module**
- The strongest early assessment checkpoint identified was **CCC / 2014B / CMA at Day 18**

## Notebooks

1. **Data Understanding** : Dataset structure, relationships, temporal information, and data quality.
2. **Data Cleaning** : Duplicate removal, missing-value handling, and validation.
3. **Feature Engineering** : Construction of early academic and engagement features.
4. **EDA** : Outcome patterns across engagement, demographic, academic, and course factors.
5. **Modeling** : Logistic Regression baseline vs Random Forest ensemble.
6. **Interpretability** : Global feature importance and individual prediction explanation.
7. **Early Warning Analysis** : Early prediction timing and assessment checkpoint analysis.
8. **Stakeholder Report** : Consolidated findings and advising recommendations.

## Validation

The modeling pipeline uses Stratified Group K-Fold cross-validation, grouping by student to prevent the same student from appearing across validation folds.

## Important Note

The raw and processed datasets and trained model are excluded from GitHub because of their size and data-distribution considerations. The notebooks document the complete analytical workflow.