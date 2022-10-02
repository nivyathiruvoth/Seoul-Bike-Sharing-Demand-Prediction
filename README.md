# Seoul-Bike-Sharing-Demand-Prediction
Predictive analysis on bike sharing demand based on regression models.

![image](https://user-images.githubusercontent.com/92729412/193471330-87328629-6df1-4207-8822-5f46d40365cf.png)


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

## Pre-processing

In this project, the dependent variable is ‘Rented bike count’, the prediction of which gives us the exact number of bikes required per hour in order to reduce the waiting time.

![image](https://user-images.githubusercontent.com/92729412/193471573-583547dc-9916-4140-9b63-7c929c966cad.png)

It can be observed that the distribution of the dependent variable is skewed. So we applied log1p transformation.

![image](https://user-images.githubusercontent.com/92729412/193471667-2487f3bd-fea7-4e71-af4e-b37821d69a8b.png)

We can observe that the features Temperature and Dew Point Temperature exhibit a high correlation. Therefore we will drop the column Dew Point temperature to prevent multicollinearity.

![image](https://user-images.githubusercontent.com/92729412/193471682-b587d268-c3b6-4682-bab7-aa0b3736ad6f.png)

VIF value is under 5. Therefore we assume that the multicollinearity between the independent variables is negligible.

![image](https://user-images.githubusercontent.com/92729412/193471707-6c99513d-7093-4da0-98cb-49b6ea579cf2.png)

We can observe from the above chart that due to high snowfall and less temperature, the number of rented bike count is deficient in the winters compared to summer and spring.
People use rental bikes primarily for short-distance travel like traveling to school or work. That's why the percentage of rented bike count is lesser on a holy day.
Since bikes are rented only on a functioning day, there is no doubt why the percentage of rented bike count is zero on a non-functioning day.

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
