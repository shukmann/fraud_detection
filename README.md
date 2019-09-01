# Fraud Detection

## Project Overview
The project is to predict probability of fraud transaction on transaction and identity data. My purpose of doing the project was to get a better understanding on how to handle complex dataset with near 400 variables. A lot of techniques was learning from other kagglers. Hopefully, this sharing could sum up what I've learnt from doing the project.

## Code
`fraud_detection.ipynb`
Main steps in the notebook
1. Data cleansing for transaction device
2. Get hour in a day from transactions (as check in EDA, day of week/month are not significant, while hour is significant that some hour with low #transaction and high #fraud)
3. Grouping transaction amount - there are many unique value in transaction amount, which model doesn't generalize well. The amount are aggregated in terms of mean and standard deviation by different cards / combination of cards to create 10 new features
4. label encoding for categorical variables
5. check max and min size of numeric variables so as to change it to a smaller type i.e. int8 for less memory consumption
6. Train a LightGBM model

## Data
There are two data files -  transaction and identity while can be download from [IEEE-CIS Fraud Detection](https://www.kaggle.com/c/ieee-fraud-detection/data) kaggle competition page
Categorical Features - Transaction
    - ProductCD
    - card1 - card6
    - addr1, addr2
    - P_emaildomain
    - R_emaildomain
    - M1 - M9
Categorical Features - Identity
    - DeviceType
    - DeviceInfo
    - id_12 - id_38

