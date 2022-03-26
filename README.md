# Credit_Fraud_Classification

## Problem Statement:
E-commerce websites often transact huge amounts of money. Whenever a huge amount of money is moved, there is a high risk of users performing fraudulent activities, e.g. using stolen credit cards, laundering money, etc.

## Objective:
The goal of this challenge is to build a machine learning model that predicts the probability that the first transaction of a new user is fraudulent.

## Details:
Electronica is an e-commerce site that sells wholesale electronics. You have been contracted to build a model that predicts whether a given transaction is fraudulent or not. You only have information about each user’s first transaction on Electronica’s website. If you fail to identify a fraudulent transaction, Electronica loses money equivalent to the price of the fraudulently purchased product. If ou incorrectly flag a real transaction as fraudulent, it inconveniences the Electronica customers whose valid transactions are flagged—a cost your client values at $8.

## Solution:

### Checking Missing Data
As one should, I started by checking whether the data was clean, and there was no missing data in the dataset. 

### Preprocessing
As the dataset was clean, Then I started working on feature selection and data preprocessing. The main problem I had was taking care of the column `Country` which had more than 150 countries which was difficult to one-hot encode because of the **Cardinality**. So I used feature engineering to select few countries column with high feature importance only. 

### EDA
Then, I started doing data analysis by plotting different columns. I used bar charts and histogram on clock chart to visualize the whole dataset. The result can be seen in the notebook I uploaded. 

### Feature Engineering
After that I did some feature engineering to extract useful feature using `featureHasher` and checked imporatant explanatory variables. Using, that I reduced the number of columns from around 170 to 10.

### Training the Model and Evaluating

Since the dataset was highly imbalanced, I had to try several methods to get results that I wanted. I tried various methods for this problem: 
1. Classification: `Random Forest`, `XGBoost` - Good results  
2. Anomaly Detection using `Isolation Forest` - Not good results
3. `AutoEncoders` using TensorFlow            - Worse result

I also tried by ubsampling using `SMOTE` but the results were not that great.

Best solution I got was by using `RandomForest`. But then again, since we wanted to reduce the recall, in other words, we wanted to reduce **False Negative** because if we predicted wrongly, the cost would be similar to the amount of purchase which is significantly larger than the $8 which is the cost if we had lower precision, in other words, had more **False Positive**. So Then I tried dropping the columns with lower feature imporatance and than trained `RandomForest` model again but results I  achieved were not much of an improvement. 

Finally, I used **Optuna** library to optimize the hyperparameters, used Stratified k-fold to check overfitting and finally achieved the **PRAUC score** of **0.51** 




