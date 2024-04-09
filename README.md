# Credit-card-fraud-detection


## Table of Contents

- [Project Overview](#Project-overview)
- [Data Sources](#Data-sources)
- [Tools](#Tools)
- [Machine Learning model used](#Machine-Learning-model-used)
- [Data Cleaning/Preparation](#Data-Cleaning/Preparation)
- [Exploratory Data Analysis](#Exploratory-Data-Analysis)
- [Data Analysis](#Data-Analysis)
- [Results/Findings](#Results/Findings)
- [Conclusion](#Conclusion)


### Project Overview

'Fraud' in credit card transactions is unauthorized usage of a credit card account by someone else and not the owner of that account’ 
Credit card frauds are on rise and now, it has become important for the credit card companies to  identify fraudulent credit card transactions so as to not charge their customers for the purchases they didn’t make. Fraud detection involves monitoring the activities of populations of its users so as to estimate, perceive or avoid objectionable behaviour, which consist of fraud, intrusion, and  defaulting.
Here, I have tried to make a Credit Card Fraud Detection model with the help of machine learning. The Credit  Card Fraud Detection Problem includes modelling past credit card transactions with the data of the ones that turned out to be fraud. This model is then used to recognize whether a new  transaction is fraudulent or not. Our objective here is to detect  100% of the fraudulent transactions while minimizing the  incorrect fraud classifications. Credit Card Fraud Detection is a  typical sample of classification.


### Data Sources

The dataset used is obtained from Kaggle website.
It consists of transactions made by credit cards in September 2013 by European cardholders, in a span of two days, having 492 frauds out of 284,807 transactions.
This dataset contains 31 columns with only numerical input variables, the result of a PCA transformation. Original features and information of customers of the dataset are not provided due to confidentiality issues and to protect sensitive data.

Dataset description-
- Features V1, V2, … V28 are the principal components obtained with PCA
- 'Time' and 'Amount’  are only features not transformed with PCA
- Feature 'Time’ consists the seconds elapsed between each transaction and the first transaction in the dataset. 
- Feature 'Amount' is the transaction Amount
- Feature 'Class' is the response variable having value 1 in case of fraud and 0for genuine transactions.


### Tools

- Google Colab - 
  - [Download here](https://colab.research.google.com/)

 
### Machine Learning model used

- Artificial Neural Nework(ANN)


### Data Cleaning/Preparation

For this dataset, in data pre-processing, apart from importing libraries, loading dataset, checking for missing values, splitting dataset into train-test datasets, we have to choose whether to perform feature scaling or not.
This is because apart from ‘Amount’ and ‘Time’, all the other input attributes are the result of PCA transformation.
Here, I tried the models on both original dataset and feature scaled(for Amount and Time) dataset, to see the difference in the accuracy and performance of our model.


### Exploratory Data Analysis

1. To understand the distribution of legit transactions & fraudulent transactions
2. To understand the statistical measures of the genuine dataset
3. To understand genuine and fraud transactions' relation with time


### Data Analysis

As we can see from the bar plot in EDA , our dataset is highly imbalanced in nature. The positive class (frauds) account for 0.172% of all transactions. So, the number of valid transactions has far outnumbered the fraudulent ones.
Thus, as to ensure the good accuracy and precision of our model and also to avoid biasing(towards genuine cases, even though it is not), we have to make the data balanced.
There are many ways to do this- Oversampling, Undersampling, etc.
Here I am using Undersampling method
Since there are 492 fraud transaction cases and  284315 genuine transaction cases, we would randomnly select 492 cases from the genuine ones and then concatenate the fraud transaction data(492) and the genuine transaction data(random 492) to get a new dataset on which we’ll work now)
This new dataset which we have now is a balanced dataset 


### Results/Findings

The analysis results are summarized as follows:
- We get to know that fraud has some relation to time, there’s higher chance of frauds happening at specific time of the day.
- A very good differentiator for the fraud transaction cases with respect to that of genuine cases is the statistical measure ‘mean’ of ‘Amount of transactions’. We can see that this mean for genuine cases is ‘88’ while that of fraud ones is ‘122’.


### Conclusion

Machine learning algorithms are used to analyze all the  authorized transactions and report the suspicious ones. These  reports are investigated by professionals who contact the cardholders to confirm if the transaction was legit or fraudulent and provide feedback to the training data algorithm to improve the fraud-detection performance over time.
