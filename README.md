# Credit Card Defaulter Prediction
## Overview
This case study aims at the case of customers default payments in Taiwan and compares the predictive accuracy of different machine learning models. The calculation that the customer defaulted or not is a classification problem .
This case study employed a binary variable, default payment (Yes = 1, No = 0), as the response variable. This study reviewed the literature and used 25 variables as explanatory variables.

## Objective
The objective is to understand different factors responsible for defaulting of customers to pay credit card payments in Taiwan & create a classification model to estimate if a customer will default or not.

## Problem Statement
Target Variable: Default payment next month
Predictors: ID, LIMIT_BAL, SEX, EDUCATION, MARRIAGE, AGE, PAY 0 to 6, BILL_AMT-1-6 & PAY_AMT-1-6.

## Univariate Data Analysis 
### Categorical Variables
![image](https://user-images.githubusercontent.com/37978451/136267691-69ab53a3-b38f-4bde-a7bf-81db7dc3aebd.png)

The Data seems equally distributed for all the categories of the categorical variables after outlier treatment.

### Continuous Variables
![image](https://user-images.githubusercontent.com/37978451/136267764-b8bdd99e-1ad3-4d2d-83ab-47a3c42848a3.png)

The Data seems equally distributed for all the continuous variables after outlier treatment.

## Bivariate GRAPHICAL Data Analysis
### Cat vs Cont
![image](https://user-images.githubusercontent.com/37978451/136267908-4a93194b-8c60-4203-a2db-50112439db5d.png)

The Data is not aligned for 0 and 1 for all the categorical variables, hence all the variables are selected.

### Cont vs Cont.
![image](https://user-images.githubusercontent.com/37978451/136267977-434da843-f641-4818-ada6-7aa9fa85bb33.png)

The Data is aligned for 0 and 1 for all the Continuous variables, there are some variations, which will be further analyzed in statistical analysis.

## Bivariate STATISTICAL Data Analysis 
### CAT Vs CONT. (ANOVA)
![image](https://user-images.githubusercontent.com/37978451/136269383-efe95cd9-45e5-4d01-9727-6e4c9a673f26.png)

### CONT. Vs CONT. (Chi-Sq.)
![image](https://user-images.githubusercontent.com/37978451/136269439-2f6d7fad-28f5-4c94-becd-9db1eab7bab1.png)
## Building a Machine Learning Models
### Logistic Regression
The first model we trained the data through is Logistic regression.
Following are the observations from the model:
Accuracy of the model on Testing Sample Data is 77%.
Accuracy values for 10-fold Cross Validation: [0.76177061 0.76736496 0.77026399 0.76549443 0.77104941 0.79258496 0.78907132 0.76881802 0.77145064 0.77154013]
The final Average accuracy of the model is 77.00%

### Decision Tree Classifier
Later we trained the data through Decision Tree.
The highest accuracy is achieved at max_depth of 3 and the criteria to measure the quality of split is set to entropy.
Following are the observations from the model:
Accuracy of the model on Testing Sample Data is 79%.
Accuracy values for 10-fold Cross Validation: [0.78488855 0.78726453 0.7949588  0.78153667 0.79858518 0.8139894
0.81851852 0.80676193 0.80587571 0.80334505]
The final Average accuracy of the model is 80.00%.

![image](https://user-images.githubusercontent.com/37978451/136268393-e8b273ac-0ae2-490c-bbb9-fbc4f076a2a0.png)

In the graph we can observe the feature importance.


Plotting Decision Tree

![image](https://user-images.githubusercontent.com/37978451/136268393-e8b273ac-0ae2-490c-bbb9-fbc4f076a2a0.png)


### Random Forest Classifier
Later we trained the data through Random Forest..
The highest accuracy is achieved at max_depth of 5, n_estimators at 150 and the criteria to measure the quality of split is set to gini.
Following are the observations from the model:
Accuracy of the model on Testing Sample Data is 80%.
Accuracy values for 10-fold Cross Validation: [0.77751748 0.7792366  0.79321518 0.7787149  0.78517415 0.80214114 0.79946215 0.7966813  0.79231415 0.79353756]
The final Average accuracy of the model is 79.00%.
![image](https://user-images.githubusercontent.com/37978451/136268549-74b78914-15a3-4fc3-826f-35d883465af8.png)

In the graph we can observe the feature importance.
![image](https://user-images.githubusercontent.com/37978451/136268582-009f98b9-a091-4d24-aebb-743ca1e6604f.png)

Plotting a Decision Tree in Random Forest

### Ada Boost
Later we trained the data through Adaboost
The highest accuracy is achieved on decision tree classifier at max_depth of 3, n_estimators at 100 and the learning rate of 0.01.
Following are the observations from the model:
Accuracy of the model on Testing Sample Data is 80%.
Accuracy values for 10-fold Cross Validation: [0.78563417 0.78623458 0.7949588  0.78339731 0.79858518 0.81338812 0.81867545 0.81061456 0.80587571 0.80334505]
The final Average accuracy of the model is 80.00%.

![image](https://user-images.githubusercontent.com/37978451/136268685-974c1cbc-1079-452e-ae1c-ce8ae7df3db3.png)

In the graph we can observe the feature importance.

### XG Boost
Later we trained the data through XGBoost.
The highest accuracy is achieved at max_depth of 3, n_estimators at 200 and at a learning_rate of 0.1 .
Following are the observations from the model:
Accuracy values for 10-fold Cross Validation: [0.78351294 0.78874752 0.79809554 0.78494911 0.80112048 0.81404866 0.81996066 0.80993642 0.80772275 0.7998916 ]
The final Average accuracy of the model is 80.00%.

![image](https://user-images.githubusercontent.com/37978451/136268752-aa420ec7-1db0-4fbf-ae54-8386a8f8e58f.png)

In the graph we can observe the feature importance.
### KNN, SVM & Naive Bayes
![image](https://user-images.githubusercontent.com/37978451/136269529-66cadfc0-15ca-43a6-a602-32ebaa297217.png)

## Observations
From the predictor significance chart we can observe that the history of past payments specially the first payment (Apr 2005) is the most important factor to decide if the person will default his/her credit card payment or not.
By checking the accuracies of all the models, the best performing model was Decision Tree with 80% accuracy. We also got similar accuracies for AdaBoost and XGBoost where we had used Decision tree as base model.
Factors other than history of past payments have really low significance in determining if the person will default or not.

## Key Takeaways
One, 
This Case study reinforces the importance of credit score.
Two,
Training the data with different models helped identify the best one.
Three, 
Decision Tree performed really well, furthermore AdaBoost and XGBoost performed equally well.
Four, 
At the end we are selecting Decision Tree as our final model for prediction.
