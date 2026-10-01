# Week 4: Supervised Learning Model Implementation

## 📌 Project Overview

This project was completed as part of Week 4 of my internship. It demonstrates a supervised machine learning workflow using Python and Scikit-learn to classify mall customers into two categories: **High Spender** and **Not High Spender**.

The project uses the Mall Customer Segmentation dataset and implements Logistic Regression as a binary classification model.

## 🎯 Objectives

- Define a binary classification problem using a public dataset.
- Prepare the data and create a target variable.
- Preprocess numerical and categorical features.
- Build a machine learning pipeline using Scikit-learn.
- Train a Logistic Regression classifier.
- Validate the model using stratified 5-fold cross-validation.
- Evaluate the model using multiple classification metrics.
- Interpret the results using a confusion matrix, ROC curve, and model coefficients.

## 📂 Dataset

**Dataset:** Mall Customer Segmentation  
**File:** `Mall_Customers.csv`  
**Source:** [Kaggle – Customer Segmentation Tutorial in Python](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python)

The dataset contains 200 customer records and includes customer ID, gender, age, annual income, and spending score.

### Features Used

| Feature | Description |
|---|---|
| Gender | Customer's gender |
| Age | Customer's age in years |
| Annual Income (k$) | Annual income in thousands of dollars |

### Target Variable

A binary target named `HighSpender` is created from the Spending Score:

- `1`: Spending Score is greater than or equal to 50.
- `0`: Spending Score is below 50.

The Spending Score is excluded from the input features because it directly determines the target label. CustomerID is also excluded because it is an identifier.

## 🛠️ Technologies Used

- Python
- Pandas
- Matplotlib
- Scikit-learn

## ⚙️ Project Workflow

1. Load and inspect the dataset.
2. Create the `HighSpender` target variable.
3. Select relevant input features.
4. Split the data into 80% training and 20% testing sets using stratification.
5. Standardize numerical features using `StandardScaler`.
6. Encode the categorical feature using `OneHotEncoder`.
7. Build a preprocessing and classification pipeline.
8. Train the Logistic Regression model.
9. Perform stratified 5-fold cross-validation on the training data.
10. Evaluate the model on the held-out test set.
11. Generate a confusion matrix, ROC curve, and coefficient visualization.
12. Export evaluation metrics and test predictions.

## 🤖 Model

**Algorithm:** Logistic Regression  
**Problem Type:** Binary Classification

Logistic Regression was selected as an interpretable baseline model. A Scikit-learn Pipeline combines preprocessing and classification to help prevent data leakage during cross-validation.

## 📊 Model Evaluation

The following results are reported in the project report for the specified dataset and train-test split.

| Metric | Test Set | 5-Fold CV Mean |
|---|---:|---:|
| Accuracy | 72.5% | 62.5% |
| Precision | 73.7% | 61.5% |
| Recall | 70.0% | 72.1% |
| F1-score | 71.8% | 66.2% |
| ROC-AUC | 0.680 | 0.647 |

The test-set accuracy was 72.5%, while the ROC-AUC was 0.680. Cross-validation results indicate that performance varies across the training folds. Since the dataset is small, these results should be treated as a baseline rather than a guarantee of performance on new customers.

**Note:** These are the results recorded in the report. Run the code on the same dataset to reproduce and verify them.

## 📈 Visualizations

The project includes visualizations to help interpret model performance:

- Target class distribution
- Confusion matrix
- Receiver Operating Characteristic (ROC) curve
- Logistic Regression coefficient plot

## 📁 Project Structure

```text
Week-4-Supervised-Learning/
├── Screenshots
├── Mall_Customers.csv
├── Mail_Seg_Week4.ipynb
├── Week4_report.docx
├── README.md
├── confusion_matrix.png
├── roc_curve.png
├── model_evaluation_metrics.csv
└── test_predictions.csv
```

The CSV dataset must be downloaded separately from Kaggle. Add generated output files after running the script.

## ⚠️ Limitations

- The dataset contains only 200 records.
- The high-spender threshold of 50 is a project-defined rule.
- Only Gender, Age, and Annual Income are used as predictors.
- Logistic Regression may not capture complex nonlinear relationships.
- Results may differ on other datasets or customer populations.
- Gender and age require careful fairness consideration in real-world customer profiling.

## 🔮 Future Improvements

- Compare Logistic Regression with Decision Tree, Random Forest, and Support Vector Machine models.
- Tune model hyperparameters using cross-validation.
- Test alternative target thresholds with a clear business justification.
- Use a larger, independent dataset for external validation.
- Evaluate probability calibration and decision thresholds.
- Investigate fairness and subgroup error rates before any practical use.

## ✅ Learning Outcomes

- Understood the supervised learning workflow.
- Created a binary classification target.
- Applied feature preprocessing using Scikit-learn.
- Implemented Logistic Regression.
- Used stratified train-test splitting and cross-validation.
- Evaluated model performance using multiple metrics.
- Interpreted classification visualizations and documented model limitations.
