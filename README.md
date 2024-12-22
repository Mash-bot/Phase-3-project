# Phase-3-project

## 1.0 ***Overview***

The main objective of this project is to solve a classification problem, that is, to use a predictive approach in our recommendations. We shall be building a classification models to be able to come up with the best model for our problem.

## 1.1 ***Business Understanding.***

A company, Seriatel company wishes to predict customer churn, specifically identifying which customers are likely to stop using their services. with this, the company will be able to take appropriate measures to retain customers that are of high risk to leave and know how to handel those customers and as a result reduce the revenue loss. Building a classification problem, the company will be able to come up with strategies to deal with the charning.

## 1.2 ***Problem Statement.***

Is our Model able to predict which customers are of high risk of churn and can we come up with strategies to deal with the churning.

## 1.3 ***Objectives.***

1. Reducing the rate of churn
2. Try and retain customers
3. Customer satisfaction

## ***Data Understanding and Sourcing***

- The data used in this classification problem is the ***SyriaTel Customer Churn***  data Sourced from ***Kaggle***
- The data contain 3332 rows and 21 columns including 1 boolean, 8 float64, 8 int64 and 4 string data types


## ***Preprocessing Approaches***

- Droped some unnecessary columns: account length, area code, phone number and state
- Dealt with outliers in some columns: Total day minutes, Total day calls, Total eve calls, Total night minutes, Total night calls.
- One Hot Encoding: international plan, voice mail plan columns were OneHotEncoded because they are categorical columns.

## Visualizations

https://github.com/Mash-bot/Phase-3-project/blob/main/images/Train%20and%20test%20AUC%20for%20max%20tree%20depth.png






