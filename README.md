# Phase-3-project

## 1.0 *** Overview***

The main objective of this project is to solve a classification problem, that is, to use a predictive approach in our recommendations. We shall be building a classification models to be able to come up with the best model for our problem.

## 1.1 *** Business Understanding.***

A company, Seriatel company wishes to predict customer churn, specifically identifying which customers are likely to stop using their services. with this, the company will be able to take appropriate measures to retain customers that are of high risk to leave and know how to handel those customers and as a result reduce the revenue loss. Building a classification problem, the company will be able to come up with strategies to deal with the charning.

## 1.2 *** Problem Statement.***

Is our Model able to predict which customers are of high risk of churn and can we come up with strategies to deal with the churning.

## 1.3 *** Objectives.***

1. Reducing the rate of churn
2. Try and retain customers
3. Customer satisfaction

## 2.0 *** Data Understanding and Sourcing***

- The data used in this classification problem is the ***SyriaTel Customer Churn***  data Sourced from ***Kaggle***
- The data contain 3332 rows and 21 columns including 1 boolean, 8 float64, 8 int64 and 4 string data types


## 2.1 *** Preprocessing Approaches***

- Droped some unnecessary columns: account length, area code, phone number and state
- Dealt with outliers in some columns: Total day minutes, Total day calls, Total eve calls, Total night minutes, Total night calls.
- One Hot Encoding: international plan, voice mail plan columns were OneHotEncoded because they are categorical columns.
- The target column, Churn was converted from Boolean values to integers.
-Data training
-Model Normalization using MinMaxScaler prior to fiting.

## 3.0 *** Visualizations ***

a. ***train and test AUC for max tree depth***

https://github.com/Mash-bot/Phase-3-project/blob/main/images/Train%20and%20test%20AUC%20for%20max%20tree%20depth.png

b. ***churn by international plan***

https://github.com/Mash-bot/Phase-3-project/blob/main/images/churn%20by%20international%20plan.png

c. ***Churners vs No_churn bar.***

https://github.com/Mash-bot/Phase-3-project/blob/main/images/churners%20vs%20No-churn.png

d. ***Train and test AUC for maximum features***

https://github.com/Mash-bot/Phase-3-project/blob/main/images/train%20and%20test%20AUC%20for%20max%20features%20values.png

e. ***Traing and test AUC for mimimum sample leaf***


https://github.com/Mash-bot/Phase-3-project/blob/main/images/train%20and%20test%20AUC%20for%20min%20sample%20leaf.png

f. ***Training and test AUC for minimum sample split***

https://github.com/Mash-bot/Phase-3-project/blob/main/images/train%20and%20test%20AUC%20for%20min%20sample%20split.png


## 4.0 *** Modeling ***

4.1 ***Fiting a Logistic regression Model***
- Sorting the absolute values of the coefficient to see features that are the most important:
The features that are the most important to our model are those with the highest absolute coefficient:

* Total night minute
* Total night charge
* Total eve minutes
* Total eve charge

- Generating predictions
- Classification report:

precision    recall  f1-score   support

           0       0.85      0.99      0.91       537
           1       0.53      0.09      0.15       102

    accuracy                           0.84       639
   macro avg       0.69      0.54      0.53       639
weighted avg       0.80      0.84      0.79       639

## 4.2 ***Improving Log-regression using SMOTE***

- classification report:

 precision    recall  f1-score   support

           0       0.94      0.79      0.86       537
           1       0.39      0.72      0.51       102

    accuracy                           0.78       639
   macro avg       0.66      0.75      0.68       639
weighted avg       0.85      0.78      0.80       639

## 4.3 ***Fiting a Decision Tree Model***

- Classification Report:

 precision    recall  f1-score   support

           0       0.94      0.95      0.95       537
           1       0.71      0.71      0.71       102

    accuracy                           0.91       639
   macro avg       0.83      0.83      0.83       639
weighted avg       0.91      0.91      0.91       639

## 4.4 ***hyperparameter tuning***
Improving the decision tree model by hyperparameter tuning

* Maximum Tree depth

* Manimum Sample Split

* Maximum features

* Minimum sample leafs

## 5.0 *** Findings, Conclusions and Recommendations ***

## 5.1 ***Findings***:
* The ROC-AUC of the logistic linear regression improved from 53% to 75% after applying SMOTE
* Logistic Regression ***First Model classification report** :

  -Precision = 0.85: Out of all instances that were predicted as class 0, 85% were actually class 0.

  -Recall = 0.99: Out of all actual class 0 instances, 99% were correctly identified by the model.

  -F1-score = 0.91: The harmonic mean of precision and recall. It's a balanced measure that considers both false positives and false negatives.

  -Precision = 0.53: Out of all instances predicted as class 1, 53% were actually class 1.

  -Recall = 0.09: Out of all actual class 1 instances, only 9% were correctly identified by the model.

  -F1-score = 0.15: This is quite low, indicating that the model has trouble balancing precision and recall for class 1.
  -Accuracy = 0.84: The overall accuracy is 84%, meaning the model correctly predicted the class in 84% of all instances. However, there is a class imbalance, which is evident here because class 0 has significantly more instances than class 1.

We therefore decide to improve our Model by Using SMOTE (Synthetic Minority Over-sampling Technique). SMOTE works by selecting examples from the minority class and generating synthetic examples by choosing a random point along the line between a sample and one of its nearest neighbors from the minority class.

* Logistic Regression ***Second Model classification report** - After Using Smote:

  -Precision = 0.94: Out of all instances that were predicted as class 0, 94% were actually class 0.

  -Recall = 0.79: Out of all actual class 0 instances, 79% were correctly identified by the model.

  -F1-score = 0.86: The harmonic mean of precision and recall. It's a balanced measure that considers both false positives and false negatives.

  -Precision = 0.39: Out of all instances predicted as class 1, 39% were actually class 1.

  -Recall = 0.72: Out of all actual class 1 instances, only 72% were correctly identified by the model.

  -F1-score = 0.51: This has improved from 0.15, indicating that we have sorted out the model's trouble in balancing precision and recall for class 1.

  -Accuracy = 0.78: The overall accuracy is 78%, meaning the model correctly predicted the class in 78% of all instances.

By applying SMOTE, the model has become much more effective at identifying the minority class (class 1), especially in terms of recall and F1-score. However, this improvement has slightly reduced the model's precision for class 0 and led to a small drop in overall accuracy.

* Decision Tree ***Model Classification report** :

  -Precision = 0.94: Out of all instances that were predicted as class 0, 94% were actually class 0.

  -Recall = 0.94: Out of all actual class 0 instances, 94% were correctly identified by the model.

  -F1-score = 0.94: The harmonic mean of precision and recall. It's a balanced measure that considers both false positives and false negatives.

  -Precision = 0.67: Out of all instances predicted as class 1, 55% were actually class 1.

  -Recall = 0.67: Out of all actual class 1 instances, only 23% were correctly identified by the model.

  -F1-score = 0.67: This is quite low, indicating that the model has trouble balancing precision and recall for class 1.

  -Accuracy = 0.89: The overall accuracy is 89%, meaning the model correctly predicted the class in 89% of all instances.

Hyperparameter tuning did not improve the decision tree model, it made it worse.

* The 4 most important important features for predicting our Target variable for this Model are as follows:

***Total Night Minutes*** - With the highest absolute coefficient of 26

***Total Night Charge*** -with an absolute coefficient of 25

***Total eve Minutes*** - with an absolute coefficient of 14

***Total eve charge*** - with ana absolute coefficient of 14

## 5.2 ***Recommendations***

  - Logistic Regression before applying SMOTE is good at identifying customers that are unlikely to churn (class 0) but less effective for churners(class 1)

  -Logistic Regresssion after applying SMOTE is a better model for predicting Churners(class 1). This is because recall for class 1 has improved, This is the best for identifying at-risk customers

  -Decision tree model has difficulty predicting churners although it provides high accuracy, it performs poorly in identifying churners

## 5.3 ***Conclusions***
***Logistic Regression (After Smote)*** would be the best model to use for identifying customers at high risk of churn. The model recall has significantly improved despite a small drop overall accuracy.

***F1-score*** improved from 0.32 to 0.62, indicating a much better balance between precision and recall. This ensures the company will be able to identify churners without too many false positives.

***The Logistic regression (After Smote)*** is the most effective model for identifying high-risk churners.









