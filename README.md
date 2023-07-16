## Overview of the Analysis

1. The purpose of the analysis.

The purpose of the model is to determine the likelihood of healthy, low risk loans or high risk loans of borrowers/potential borrowers in the testing set.

2. Explain what financial information the data was on, and what you needed to predict.

Factors considered in the analysis included data on:

the size of the loan
loan interest rate
borrower's income
borrower's debt to income ratio
the number of accounts held by borrower
derogatory marks (against the borrower)
borrower's total debt

The 77,536 data points in the original dataset, was split into training and testing sets. The training set was used to build an initial logistic regression model (LR Model 1) using the scikit-learn's, LogisticRegression module. Logistic Regression Model 1 was then applied to the testing dataset. 

The resampled logistic regression model (LR Model 2), was resampled with the RandomOverSampler module from imbalanced-learn to generate 56,277 data points each for healthy, low risk and high risk loans, based on the original dataset.

3. Provide basic information about the variables you were trying to predict (e.g., `value_counts`).

The intial model was drawing from a dataset that had 75,036 healthy, low risk loan data points and 2,500 high risk data points. In the second model, the RandomOverSample resampled the training data and to ensure that the logistic regression model had an equal number of data points to draw from.

## Results

Logistic Regression Model 1:

Precision:  93% average 
            100% Predicting healthy low risk loans
            87% Predicting high risk loans

Accuracy:   94%

Recall:     95% average
            100% Predicting healthy, low risk loans
            89% Pedicting high-risk loans)

Logistic Regression Model 2:

Precision:  93% average
            100% Predicting healthy, low risk loans
            87% Predicting high risk loans
            
Accuracy: 100%

Recall: 100%

## Summary

From the analysis, the Logistic Regression Model 2 is less likely to predict false negative results. However, based on the confusion matrices for each model, Logistic Regression Model 2 predicted slightly more false positives (low risk when actually high risk).

Logistic Regression Model 2 had fewer false predictions of the testing data overall and would be the best model to use based on the high accuracy and recall of this model.  However, 
as the goal of the model is to determine potential borrowers of high-risk loans, neither model scores above 90% precision, and therefore I do not recommend. 

