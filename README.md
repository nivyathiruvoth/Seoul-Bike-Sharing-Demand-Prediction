# readme

<p align="center"> 

<img src="https://t3.ftcdn.net/jpg/00/99/47/54/360_F_99475491_0cRIhy4v3DheDHoRLbWcfGZ9qFcWmv1d.jpg" height="150px">

</p>

<h1 align="center"> Bike Sharing Demand Prediction
 </h1>

<h3 align="center"> AlmaBetter Verified Project - <a href="https://www.almabetter.com/"> AlmaBetter School </a> </h5>

<p align="center"> 
<img src="https://sophiesu.net/wp-content/uploads/2021/01/Bike-Sharing-Demand-1194x501.jpg" height="400px">
</p>

<p> </p>

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<h2> :floppy_disk: Table of Content</h2>

 
  * [Introduction](#Introduction)
  * [Problem Statement](#Problem-Statement)
  * [Objectives](#Objectives)
  * [Dataset Information](#dataset-information)
  * [Tools and Technologies used](#tools-and-technologies-used)
  * [Steps involved](#Steps-involved)
  * [Algorithms used](#Algorithms-used)
  * [Conclusion](#Conclusion)


![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)


<h2> 📄 Introduction</h2>

A bicycle-sharing system, bike share program, public bicycle scheme, or public bike share (PBS) scheme, is a shared transport service in which bicycles are made available for shared use to individuals on a short term basis for a price or free.

Predicting bike sharing demand can help bike sharing companies to allocate bikes better and ensure a more sufficient circulation of bikes for customers.


![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)


<h2> ❓ Problem Statement</h2>

Currently Rental bikes are introduced in many urban cities for the enhancement of mobility comfort. It is important to make the rental bike available and accessible to the public at the right time as it lessens the waiting time. Eventually, providing the city with a stable supply of rental bikes becomes a major concern. The crucial part is the prediction of bike count required at each hour for the stable supply of rental bikes.


![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<h2> 🎯 Objectives: </h2>

1. Prediction of bike count required at each hour for the stable supply of rental bikes in bike sharing system.

2. Gathering information regarding the factors that affect this prediction the most.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<h2> :book: Data Summary </h2>

The data set was taken from Seoul, the Capital of South Korea and contained 8760 bike-rented details. It also consisted of features such as temperature, visibility, humidity, holiday, functioning day, rainfall, snowfall etc based on which we are trying to predict the rental bike count. The observations in the dataset were recorded during a span of 365 days, from December 2017 to November 2018.

The Seoul Bike  Dataset contains the following information:

* **Date** - The date of each observation in the format 'year-month-day'
* **Hour** - Hour of the day
* **Temperature** - Temperature recorded in the city in Celsius (°C).
* **Humidity** - Relative humidity in %
* **Wind speed** - Speed of the wind in m/s
* **Visibility** - measure of distance at which object or light can be clearly discerned in units of 10m
* **Dew point temperature** - Temperature recorded in the beginning of the day in Celsius(°C).
* **Solar radiation** - Intensity of sunlight in MJ/m^2
* **Rainfall** - Amount of rainfall received in mm
* **Snowfall** - Amount of snowfall received in cm
* **Seasons** - Season of the year (Winter, Spring, Summer, Autumn)
* **Holiday** - Whether the day is a Holiday or not (Holiday/No holiday)
* **Functional Day** -Whether the rental service is available (Yes-Functional hours) or not (No-Non functional hours)
* **Rented Bike count** - Count of bikes rented at each hour (target variable)


![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<h2> 📑 Steps involved </h2>

1. Exploring the data: Analyzing the features and target variable, checking for null values and duplicates, plotting the distribution of target variable etc.

2. Treating numerical and categorical features separately, VIF Analysis, Encoding, Outlier detection etc.

3. Train test split, Transformation, Scaling etc.

4. Develop different models and evaluate them.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<h2>🛠️ Pre-processing </h2>

In this project, the dependent variable is ‘Rented bike count’, the prediction of which gives us the exact number of bikes required per hour in order to reduce the waiting time.

![image](https://user-images.githubusercontent.com/92729412/194842399-829fe471-f014-425b-aeac-b0a69b926ca0.png)

It can be observed that the distribution of the dependent variable is skewed. So we applied log1p transformation.

![image](https://user-images.githubusercontent.com/92729412/194842434-3478d962-e618-45d8-a88c-5726c735e169.png)

We can observe that the features Temperature and Dew Point Temperature exhibit a high correlation. Therefore we will drop the column Dew Point temperature to prevent multicollinearity.

![image](https://user-images.githubusercontent.com/92729412/194842482-fd3c3d78-d67b-4a8f-834e-b4573cfc57bb.png)

VIF value is under 5. Therefore we assume that the multicollinearity between the independent variables is negligible.

![image](https://user-images.githubusercontent.com/92729412/194842509-3ce4caaf-0077-4e03-956f-fdf74fc1fdf3.png)

We can observe from the above chart that due to high snowfall and less temperature, the number of rented bike count is deficient in the winters compared to summer and spring. People use rental bikes primarily for short-distance travel like traveling to school or work. That's why the percentage of rented bike count is lesser on a holy day. Since bikes are rented only on a functioning day, there is no doubt why the percentage of rented bike count is zero on a non-functioning day.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<h2>💻 Algorithms used</h2>

* Linear Regression

* Random Forest

* Gradient Boosting Machine

* XGBoost

<h3> Best Hyper-parameters </h3>

* Random Forest:

max_depth : 8

min_samples_leaf : 40

min_samples_split : 50

n_estimators : 100

* GBM:

max_depth : 8

min_samples_leaf : 40

min_samples_split : 50

n_estimators : 80

* XGBoost:

eval_metric : rmse

max_depth : 6

n_estimators : 500

<h3> Model Comparison </h3>

All the models are evaluated on the basis of following evaluation metrics.

![image](https://user-images.githubusercontent.com/92729412/194840929-6cfe7fcb-6422-41f0-9349-9ba80e9cfd03.png)

<h2> :bulb: Conclusion</h2>

This project focus on predicting the bike-sharing demand using Seoul Dataset.

* In contrast to Linear Regression, the results demonstrate that XGBoost, Random Forest, and GBM algorithms performed well on the dataset.

* Among these three models, XGBoost is found to have better performance with least test-MAE(139.62) and highest test - R2 Score(87%). Therefore XGBoost algorithm can be used as an effective tool for Bike Sharing Demand Prediction.

* Analyzing feature importance showed that functioning day, temperature, and rainfall were the most influential variables in predicting the rental bike demand at each hour for all the models.

* The intriguing relationship between the variables that can have an immediate impact on the dependent variable, "Rented Bike Count," is revealed by this project.

* As a result of this project, bike-sharing companies can better predict the hourly demand for bikes and enhance the customer experience.
 
![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<!-- CREDITS -->
<h2 id="credits"> :scroll: Credits</h2>

Nivya T | Avid Learner | Data Scientist | Machine Learning Engineer | Deep Learning Enthusiast

<p> <i> Contact me for Data Science Project Collaborations</i></p>


[![LinkedIn Badge](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/nivyathiruvoth/)
[![GitHub Badge](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/nivyathiruvoth)
[![Medium Badge](https://img.shields.io/badge/Medium-1DA1F2?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@nivyathiruvoth)
[![Resume Badge](https://img.shields.io/badge/resume-0077B5?style=for-the-badge&logo=resume&logoColor=white)](https://drive.google.com/file/d/1o5VojatmPA-amnQkOJ-xb6yIq_Jof8D2/view?usp=sharing)
