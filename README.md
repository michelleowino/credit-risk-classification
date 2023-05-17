
# Overview of the Analysis

<img width="547" alt="Screenshot 2023-05-17 at 12 40 34 AM" src="https://github.com/michelleowino/credit-risk-classification/assets/119654958/6dd87cd8-3ed9-4e32-a4f5-c7fed352d504">

## Purpose
The purpose of this analysis is to build, train and evaluate a model based on loan risk to identify the creditworthiness of borrowers.

## Data
The dataset is of historical lending activity from a peer-to-peer lending services company. The dataset includes information about the borrower’s loan size, interest rate, income, debt to income, number of accounts, derogatory marks, total debt, and loan status. The goal is to predict healthy loans and high-risk loans. 

## Method
Method used to analyze the data was LogisticRegression. In the context of creditworthiness assessment, LogisticRegression is best because it’s a binary classification task and it’s a statistical model that estimates the probability of an instance belonging to a particular class using a logistic function.

Resampling method is employed to address class imbalance issues in the dataset. Class imbalance occurs when one class (e.g., high-risk loans) is underrepresented compared to the other class (e.g., healthy loans). These methods help to ensure that the model receives a balanced representation of both classes during training.

## Steps
The steps taken as part of the analysis included, preprocessing the data, instantiating the logistic regression model, fitting the model using the training data and making predictions. 

I started off by splitting the data into training and testing sets. I created the labels set (`y`) from the loan_status column, and then created the features (`x`) DataFrame from the remain columns. I checked the balance of the labels variable (`y`) by using the `value_counts` function, then split the data into training and testing datasets by using `train_test_split`. 

Next step was to create a logistic regression Model with the original data. I fit a logistic regression model by using the training data (`X_train` and `y_train`). Saved the predictions for the testing data labels by using the testing feature data (`X_test`) and the fitted model.

## Results

### Machine Learning Model 1 (Original Data):

Below are the results for logistic regression model 1 predictions for both the `0` (healthy loan) and `1` (high-risk loan) labels. 

For `0` (healthy loan)
-	The model has a precision of 1.00, meaning that it's correct 100% of the time. 
-	The model has a recall of 1.00, which means that it correctly identifies 100% of the actual healthy loans. 
-	The F1-score is 1.00, which reflects a perfect balance between precision and recall for healthy loans.                                                                                     

For `1` (high-risk loan)
-	The model has a precision of 0.85, meaning that it's correct about 85% of the time. 
-	The model has a recall of 0.91, which means that it identifies approximately 91% of the actual high-risk loans. 
-	The F1-score is 0.88, which indicates a good balance between precision and recall for high-risk loans.


### Machine Learning Model 2(Resampled Data):
 
Below are the results for logistic regression model 2 (fit with oversampled data) predictions for both the `0` (healthy loan) and `1` (high-risk loan) labels. 

For `0` (healthy loan)
-	The model has a precision of 1.00, meaning that it's correct 100% of the time. 
-	The model has a recall of 0.99, which means that it correctly identifies 99% of the actual healthy loans. 
-	The F1-score is 1.00, which reflects a perfect balance between precision and recall for healthy loans. 

For `1` (high-risk loan)
-	The model has a precision of 0.85, meaning that it's correct about 85% of the time. 
-	The model has a recall of 1.00, which means that it identifies approximately 100% of the actual high-risk loans. 
-	The F1-score is 0.92, which indicates a great balance between precision and recall for high-risk loans.

#### Both models have an accuracy of 99%. 

## Summary

Both models have high precision, indicating that they correctly predict healthy loans with a high accuracy. However, Model 1 has a perfect recall and F1-score of 1.00, suggesting that it captures all actual healthy loans and achieves a balance between precision and recall.

When we compare the performance of each model for predicting the 1 (high-risk loan) label, both models have similar precision scores for predicting high-risk loans. However, Model 2 has a perfect recall of 1.00, indicating that it captures all actual high-risk loans. Model 2 also has a slightly higher F1-score, suggesting a better balance between precision and recall for the high-risk loans.

Considering these metrics, we can conclude that Model 1 performs better for predicting healthy loans, as it achieves a perfect balance between precision and recall. On the other hand, Model 2 performs better for predicting high-risk loans, as it has a perfect recall and a slightly higher F1-score.

The performance of the models will depend on the problem we are trying to solve. Considering the goal of identifying creditworthiness, Model 2 seems to perform better. I would recommend this model because it achieves a perfect recall of 1.00 for the 1 label, meaning it correctly identifies all high-risk borrowers. This is particularly important in the context of creditworthiness assessment, as correctly identifying high-risk borrowers helps mitigate potential financial risks. Additionally, it has a slightly higher F1-score of 0.92, which indicates a better balance between precision and recall compared to Model 1.

## References
Data for this dataset was generated by edX Boot Camps LLC, and is intended for educational purposes only.
