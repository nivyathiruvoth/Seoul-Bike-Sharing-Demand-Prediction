# Seoul-Bike-Sharing-Demand-Prediction
Predictive analysis on bike sharing demand based on regression models.

## Introduction

A bicycle-sharing system, bike share program, public bicycle scheme, or public
bike share (PBS) scheme, is a shared transport service in which bicycles are made
available for shared use to individuals on a short term basis for a price or free.

Predicting bike sharing demand can help bike sharing companies to allocate bikes
better and ensure a more sufficient circulation of bikes for customers.

## Problem Statement

Currently Rental bikes are introduced in many urban cities for the enhancement
of mobility comfort. It is important to make the rental bike available and
accessible to the public at the right time as it lessens the waiting time.
Eventually, providing the city with a stable supply of rental bikes becomes a
major concern. The crucial part is the prediction of bike count required at each
hour for the stable supply of rental bikes.

## Objectives

1. Prediction of bike count required at each hour for the stable supply
of rental bikes in bike sharing system.

2. Gathering information regarding the factors that affect this
prediction the most.

## Data Summary

Date : year-month-day

Rented Bike count - Count of bikes rented at each hour

Hour - Hour of he day

Temperature-Temperature in Celsius

Humidity - %

Windspeed - m/s

Visibility - 10m

Dew point temperature - Celsius

Solar radiation - MJ/m2

Rainfall - mm

Snowfall - cm

Seasons - Winter, Spring, Summer, Autumn

Holiday - Holiday/No holiday

Functional Day - NoFunc(Non Functional Hours), Fun(Functional hours)

## Steps Involved

1. Exploring the data: Analyzing the features and target variable, checking
for null values and duplicates, plotting the distribution of target variable etc.

2. EDA: Treating numerical and categorical features separately, VIF
Analysis, Encoding, Outlier detection etc.

3. Preprocessing of data: Train test split, Transformation, Scaling etc.

4. Creating models: Create different models and evaluate them using
different metrics.

## Models used

Linear Regression

Random Forest

Gradient Boosting Machine

XGBoost

## Best Hyper-parameters

### Random Forest:

max_depth : 8

min_samples_leaf : 40

min_samples_split : 50

n_estimators : 100

### GBM:

max_depth : 8

min_samples_leaf : 40

min_samples_split : 50

n_estimators : 80


### XGBoost:

eval_metric : rmse

max_depth : 6

n_estimators : 500

## Model Comparison

All the models are evaluated on the basis of following evaluation metrics.

![image](https://user-images.githubusercontent.com/92729412/188855490-15f3516e-c1bd-47cd-b354-e10e46abba6e.png)


## Conclusion

This project focus on predicting the bike-sharing demand using Seoul Dataset.

* In contrast to Linear Regression, the results demonstrate that XGBoost, Random Forest, and GBM algorithms performed well on the dataset. 
* Among these three models, XGBoost is found to have better performance with least test-MAE(139.62) and highest test - R2 Score(87%). Therefore XGBoost algorithm can be used as an effective tool for Bike Sharing Demand Prediction.
* Analyzing feature importance showed that functioning day, temperature, and rainfall were the most influential variables in predicting the rental bike demand at each hour for all the models.
* The intriguing relationship between the variables that can have an immediate impact on the dependent variable, "Rented Bike Count," is revealed by this project. 
* As a result of this project, bike-sharing companies can better predict the hourly demand for bikes and enhance the customer experience.
