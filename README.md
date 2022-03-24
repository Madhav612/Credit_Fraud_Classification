# Credit_Fraud_Classification

## Problem Statement:
E-commerce websites often transact huge amounts of money. Whenever a huge amount of money is moved, there is a high risk of users performing fraudulent activities, e.g. using stolen credit cards, laundering money, etc.

## Objective:
The goal of this challenge is to build a machine learning model that predicts the probability that the first transaction of a new user is fraudulent.

## Details:
Electronica is an e-commerce site that sells wholesale electronics. You have been contracted to build a model that predicts whether a given transaction is fraudulent or not. You only have information about each user’s first transaction on Electronica’s website. If you fail to identify a fraudulent transaction, Electronica loses money equivalent to the price of the fraudulently purchased product. If ou incorrectly flag a real transaction as fraudulent, it inconveniences the Electronica customers
whose valid transactions are flagged—a cost your client values at $8.

## Solution:
As one should, I started by checking whether the data was clean, and there was no missing data in the dataset. As the dataset was clean, Then I started working on feature selection and data preprocessing. The main problem I had was taking care of the column `Country` which had more than 150 countries which was difficult to one-hot encode because of the **Cardinality**. So I used feature engineering to select few countries column with high feature importance only. Then, I started doing data analysis by plotting different columns. I used bar charts and histogram on clock chart to visualize the whole dataset. The result can be seen in the notebook I uploaded. After that I did some feature engineering to extract useful feature using `featureHasher` and checked imporatant explanatory variables.
