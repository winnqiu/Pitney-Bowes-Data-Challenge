# Pitney-Bowes-Data-Challenge
Pitney Bowes provides a dataset that contains daily info of their mailing meters to monitor these machines, and used these data to predict whether a meter will fail in the next 7 days to have sufficient resources in hand to keep their customers happy. They provide a train.csv which contains 55 columns and 40500 rows, and a test.csv file contains 54 columns and 4500 rows. The target variable is fail_7 in the train dataset, the goal is to use the model we build to predict whether the mailing meter in the test dataset will fail in the next 7 days. 

## Performance metric to use
The most important performance metric will be Recall score. Since we are predicting whether a meter will fail in the next 7 days and we need to avoid any fall negatives, recall score will be the most important indicator of our models.

## Data cleaning
There are lots of attributes that are highly correlated, and some attribute that can be calculated by a subset of the attributes,such as avg_time_charging/discharging can be calculated using avg_time_charging/discharging_lag1 to lag 14. What I did is to drop those highly correlated columns and those lag columns. The rest of the dataset still has some missing values, but since the number of missing values is small, so I decided to drop the rows with the missing values.

## Base models
Decison Tree, Logistic Regression and Naive Bayes. 

## Feature Engineering
Although I tried to use Principal Components Analysis to reduce the dimensions, but it turns out to have lower recall score on all the models, I decided to keep all the predictors.

## Outcome
The Naive Bayes model seems to have the highest recall score, although it is still quite low, that's the best option due to time limit and my knowlegde at that time. I used the Naive Bayes model to create a fail_7 column for the test.csv file. 

## Dataset
The dataset is not included in this repository to avoid any issue.
