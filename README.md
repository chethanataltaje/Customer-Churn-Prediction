# Customer-Churn-Prediction
## Overview
 This project focuses on analyzing customer data from a telecommunications company to identify those at risk of churning.It addresses the challenge of class imbalance in the dataset and evaluates different approaches to improve predictions.

### Dataset
* Source: The dataset includes customer demographics, account details, and service usage patterns.
* Features: Various attributes such as tenure, payment method, and internet service type.
* Target Variable: Churn (binary: 1 for churn, 0 for no churn).

### Problem Statement
The dataset is imbalanced, meaning there are significantly more non-churners than churners. This imbalance can bias models toward predicting non-churners. To address this, we evaluate two approaches:
1. A baseline logistic regression model without addressing the imbalance.
2. A model using SMOTE (Synthetic Minority Oversampling Technique) to balance the training data.

### Project Workflow
1. Data Preprocessing
    * Null Values: Missing values in TotalCharges were filled using the median value.
    * Categorical Variables: Transformed into numerical representations using one-hot encoding.
    * Feature Scaling: Standardized numerical features (tenure, MonthlyCharges, TotalCharges) using StandardScaler for better model performance.

2. Exploratory Data Analysis (EDA)
EDA helped uncover patterns and insights:
    * Histograms: Visualized distributions of numerical features.
    * Box Plots: Identified potential outliers in numerical data.
    * Correlation Heatmap: Showed relationships between numerical features.
    * Churn Distribution: Highlighted the imbalance in the target variable.

3. Model Building
 Baseline Model (Without SMOTE)
    * Algorithm: Logistic Regression
    * Performance:
                * Accuracy: 80%
                * Precision (Churn): 66%
                * Recall (Churn): 56%
                * F1-Score (Churn): 60%

SMOTE-Adjusted Model
     * Algorithm: Logistic Regression with SMOTE applied to the training data.
     * Performance:
                * Accuracy: 73%
                * Precision (Churn): 50%
                * Recall (Churn): 70%
                * F1-Score (Churn): 58%
                
4. Model Evaluation
   * The baseline model has better overall accuracy but struggles with recall for churners.
   * The SMOTE-adjusted model improves recall, which is essential for identifying churners, albeit with lower precision.
     
5. Conclusion
   * The SMOTE-adjusted model is better suited for this problem as it prioritizes recall, helping identify churners more effectively.
   * Business decisions should focus on reducing false negatives to retain at-risk customers.
