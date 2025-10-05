#  Health Readmission Model Analysis

## Objective
The goal of this assessment is to build and compare multiple machine learning models to predict patient readmission based on the UCI Diabetic Readmission Dataset. Models include:
- Random Forest
- XGBoost
- Support Vector Machine (SVM)

## Model Evaluation Metrics
Each model was evaluated using key performance metrics:
 Accuracy: Overall correctness of predictions  
 Precision: Correct positive predictions over total predicted positives  
 Recall/Sensitivity: Correct positive predictions over total actual positives  
 F1 Score: Balance between Precision and Recall  
 AUC (Area Under Curve): Model’s ability to distinguish between classes  
 Brier Score: Measures the accuracy of probabilistic predictions (lower is better)

## Updated Model Comparison Table

| Model         | Accuracy  | Precision  | Recall/Sensitivity | F1 Score | AUC     | Brier  |
|---------------|-----------|------------|--------------------|----------|---------|------- |
| XGBoost       | 0.6460    | 0.6316     | 0.5567             | 0.5918   | 0.7031  | 0.2169 |
| Random Forest | 0.6447    | 0.6394     | 0.5256             | 0.5769   | 0.6939  | 0.2207 |
| SVM           | 0.6245    | 0.6237     | 0.4407             | 0.5164   | 0.6533  | 0.2298 |


## Analysis and Observations
1. XGBoost achieved the best overall performance with:
    Highest **AUC (0.7031)** → best at distinguishing between readmitted and non-readmitted patients.  
    Lowest **Brier Score (0.2169)** → most reliable probability estimates.
2. Random Forest performed closely with slightly better precision, showing it’s conservative in predicting readmissions.
3. SVM showed lower recall and AUC, indicating it missed more true positives compared to tree-based models.
4. A 65% accuracy is reasonable for healthcare prediction tasks, especially since medical readmission data is often imbalanced and complex.
5. Future improvements may include:
    Hyperparameter tuning with GridSearchCV or Optuna.
    Addressing class imbalance with SMOTE or class weighting.
    Adding more patient-specific features or time-based information.


## Conclusion
Among the models tested, XGBoost performed the best overall, providing a good balance of accuracy, reliability, and predictive power. Despite a modest accuracy (~65%), it’s considered acceptable for medical datasets where perfect prediction is less realistic, and model interpretability matters most.

