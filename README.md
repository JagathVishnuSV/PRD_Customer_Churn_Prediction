# Customer Churn Prediction

## Project Overview
This project focuses on predicting customer churn for a bank using machine learning. Churn refers to customers who leave the bank. The objective is to build models that can identify customers who are likely to exit, allowing the business to take preventive actions.

The dataset used is `Churn_Modelling.csv`.

## Problem Statement
Customer retention is critical for banking institutions. Losing customers impacts revenue and growth. This project builds predictive models to classify whether a customer will churn (`Exited = 1`) or stay (`Exited = 0`).

## Dataset Description
The dataset contains customer-level information such as:
*   `CreditScore`
*   `Geography`
*   `Gender`
*   `Age`
*   `Tenure`
*   `Balance`
*   `NumOfProducts`
*   `HasCrCard`
*   `IsActiveMember`
*   `EstimatedSalary`
*   `Exited` (Target Variable)

> **Note:** Irrelevant columns like `RowNumber`, `CustomerId`, and `Surname` were removed before modeling.

## Data Preprocessing
*   **Cleaning:** Removed identifier columns that do not contribute to prediction.
*   **Feature Engineering:** Created additional features:
    *   `Balance_per_Product`
    *   `Age_group` (categorized age into ranges)
*   **Separation:** Separated numerical and categorical columns.
*   **Transformation:**
    *   Applied `StandardScaler` to numerical features.
    *   Applied `OneHotEncoding` to categorical features.
*   **Splitting:** Split the dataset into training (80%) and testing (20%) sets using stratified sampling to maintain class distribution.
*   **Imbalance Handling:** Applied **SMOTE** on the training data to handle class imbalance.

## Models Used
Three machine learning models were trained and compared:
1.  **Logistic Regression**
2.  **Random Forest Classifier**
3.  **XGBoost Classifier**

Each model was trained on the processed training dataset and evaluated on the test dataset.

## Evaluation Metrics
The models were evaluated using the following metrics:
*   ROC AUC Score
*   Precision
*   Recall
*   F1 Score
*   Confusion Matrix
*   Classification Report

ROC curves were plotted for visual comparison. The best-performing model was selected based on the **F1 Score**.

## Model Saving
For each trained model, the following actions were performed:
*   The preprocessing pipeline and trained model were saved using `joblib`.
*   ROC curve plots were saved.
*   Feature importance plots were generated (if supported by the model).
*   SHAP summary plot was generated for interpretability (if applicable).
*   A summary file containing model performance metrics was saved.

## Output Artifacts
The following outputs were generated:
*   Trained model files (`.joblib`)
*   ROC curve image
