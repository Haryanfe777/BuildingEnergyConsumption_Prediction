# Building Energy Consumption Prediction
## Overview
This project aims to predict the Site Energy Usage Intensity (Site EUI) for buildings using a dataset of over 75,000 observations collected across 7 years. By analyzing building characteristics and climatic data, the goal is to assist policymakers in targeting energy-efficient renovations, thereby reducing greenhouse gas emissions and tackling climate change.

Through this project, a scikit-learn pipeline was developed to preprocess data, build machine learning models, and optimize hyperparameters to achieve accurate predictions.

## Features
The dataset contains detailed information about building characteristics, meteorological conditions, and annual energy usage. Key features include:

1. Building Attributes: Floor area, facility type, construction year, and energy star rating.
2. Weather Data: Annual temperature, precipitation, snowfall, and extreme temperature days.
3. Target Variable: Site EUI (amount of heat and electricity consumed).

## Goals
1. Perform exploratory data analysis (EDA) to understand the dataset and identify patterns or anomalies.  
2. Build a scikit-learn pipeline for:  
   a. Preprocessing data based on feature types (categorical, numerical, etc.).  
   b. Scaling and encoding features appropriately.  
   c. Handling missing values.  
   d. Train and optimize machine learning models to minimize the Root Mean Square Error (RMSE).  
   e. Tune hyperparameters for model performance improvements.  


## Data
The dataset contains more than 75,000 observations with the following types of features:

1. Building Characteristics:
Floor area, year built, building class, facility type, and elevation.
Energy star rating (indicating efficiency).
2. Climatic Variables:
Annual average temperature, precipitation, snowfall, and extreme weather days.
Cooling and heating degree days.
3. Wind and Fog Data:
Maximum wind speed, foggy days, and wind direction for peak wind speeds.
4. Target:
Site EUI: Energy consumption per square foot of the building.

## Methods

1. **Exploratory Data Analysis (EDA)**  
   - Visualized distributions of key variables like floor area, energy star ratings, and Site EUI.  
   - Examined relationships between climatic variables and energy usage.  
   - Identified missing data, duplicates, and outliers.

2. **Preprocessing with Scikit-Learn Pipelines**  
   - **Categorical Data:**  
     a. Handled using one-hot encoding for building classes and facility types.  
     b. Imputed missing values with mode.  
   - **Numerical Data:**  
     a. Dropped duplicates.  
     b. Scaled using standardization.  
     c. Dropped columns with more than 70% missing values and imputed others with median values.  
     d. Used outlier cappers to cushion the effect of outlier values.  
     e. Replaced anomalous or NaN values with 0.  
   - **Feature Engineering:**  
     a. Created derived features, such as extreme weather days grouped by thresholds (e.g., days below 0°F) and average seasonal temperatures.  
     b. Used PCA to reduce columns' dimensionality.

3. **Model Training**  
   - Built multiple machine learning models using the engineered and non-engineered dataset, including:  
     a. Linear Regression  
     b. Random Forest Regressor  
     c. Gradient Boosting Regressor  
     d. Support Vector Machine  
   - Tuned hyperparameters using:  
     a. K-Fold Cross Validation  
     b. GridSearchCV  
     c. ElasticNetCV  
     d. RandomizedSearchCV  


## ML Pipeline
Built an extensive Machine Learning Pipeline that automates all the preprocessing steps with model fitting and hypeparameters tuning.

![Screenshot 2024-11-28 010303](https://github.com/user-attachments/assets/4d0408aa-8f4d-45fa-9063-7e0a566f6d6d)



## Evaluation
1. Evaluated models using Root Mean Square Error (RMSE).
2. Compared model performances and selected the best-performing model.

## Results

![Screenshot 2024-11-27 185300](https://github.com/user-attachments/assets/71651bfe-b284-4f18-ae74-95408908c0bb)


Key Insights:

1. Gradient Boosting performed best, highlighting its ability to handle non-linear relationships and complex data distributions.
2. Extreme weather days and energy star ratings were significant predictors of energy consumption.

## Technologies Used

1. **Programming:**  
   - Python  

2. **Libraries:**  
   - **Data Manipulation:** Pandas, NumPy  
   - **Visualization:** Matplotlib, Seaborn  
   - **Machine Learning:** Scikit-learn, XGBoost  

3. **Tools:**  
   - Scikit-learn Pipelines  
   - GridSearchCV  

   
## Conclusion
This project demonstrates the importance of accurate energy consumption predictions in combating climate change. By analyzing building and weather data, the machine learning models developed here can help policymakers identify high-priority buildings for energy efficiency improvements, ultimately reducing greenhouse gas emissions and promoting sustainability.
