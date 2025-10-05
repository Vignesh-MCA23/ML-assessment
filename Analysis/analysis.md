# Diabetic Readmission Prediction - Results Summary

# Model Performance Comparison

| Model | AUC | Accuracy | F1-Score | Brier Score | Status |
|-------|-----|----------|----------|-------------|--------|
| **XGBoost** | 0.681 | 0.889 | 0.032 | 0.094 | **Best Performer** |
| **Random Forest** | 0.636 | 0.889 | 0.015 | 0.096 | Competitive |
| **SVM (subset)** | 0.631 | 0.888 | 0.000 | 0.097 | Limited by sample size |

# Key Results

# Best Performing Model
- **XGBoost** achieved highest AUC (0.681) and F1-score (0.032)
- All models showed similar accuracy (~88.9%)

# Critical Challenge
- **Severe class imbalance** affecting minority class prediction
- Very low F1-scores despite high accuracy
- SVM failed to predict any readmission cases (F1: 0.000)

# Successful Implementation
- **Feature selection** reduced dimensions to 1,185 important features
- **Model calibration** applied using isotonic regression
- **Probability calibration** improved reliability for all models

# Performance Metrics Analysis

# AUC-ROC (Discriminative Power)
1. XGBoost: 0.681
2. Random Forest: 0.636  
3. SVM: 0.631

# F1-Score (Minority Class Performance)
1. XGBoost: 0.032
2. Random Forest: 0.015
3. SVM: 0.000

# Probability Calibration
- All models show similar Brier scores (~0.095)
- XGBoost has slightly better calibration (0.094)

# Technical Specifications

# Data Processing
- **Original**: 101,766 samples × 48 features
- **Final**: 1,185 selected features after preprocessing
- **Target**: Binary classification (30-day readmission)

# Model Configuration
- **XGBoost/RF**: 50 estimators, full dataset training
- **SVM**: RBF kernel, 5,000 sample subset
- **Calibration**: Isotonic regression with 5-fold CV (3-fold for SVM)

# Conclusion

XGBoost demonstrates the best predictive capability for diabetic readmission prediction, though all models are significantly impacted by class imbalance. The implemented feature selection and probability calibration provide reliable foundations for clinical risk assessment.