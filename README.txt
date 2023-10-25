# House Price Prediction Case Study 

A US-based housing company named "Surprise Housing" uses data analytics to purchase houses at a price below their actual values and flip them on at a higher price. It has decided to enter the Australian market and so it is looking at prospective properties to buy to enter the market. For this purpose, the company wants to know

Which factors are significant in predicting the price of a house
How well those factors describe the price of a house.
Our goal:
To create a regression model for the target variable named "SalePrice" based on collected data set and using regularisation technique in order to predict the actual value of the prospective properties accurately so that it can be decided whether it will be good to invest in those or not.

Business Objective:

To understand how exactly the SalePrice vary with the features so that this knowledge can be used to concentrate on areas that will yield high returns
To understand the pricing dynamics of a new market.


## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

## General Information
- The main objective of this analysis is to create a linear regression model to understand which independent variables/attributes (predictor) are mostly impacting outcome variable "cnt" (count of total rental bikes)
- Steps followed for this analysis: 
  1. Reading and cleaning the Data
     - Input dataset used for this analysis had 730 rows and 16 columns
     - The data cleaning step included
        1. Rounding up digit after decimal  by 3 
        2. Converting integer values to corresponding categorical values 
        3. Checking columns have same values or not
        4. Remove columns which are not required for analysis
  2. Visualising the data - 
     -  Created different plots to understand the relationship (specifically to understand linear relationship) between different sets of variables 
  3. Data preparation for Modeling
        1. Converting categorical variables to dummy variables - so that they become suitable for model building 
        2. Splitting data into Training and Test sets at 70% (for training data) and 30% (for evaluating data) ratio respectively
        3. Rescaling features using Min-Max scaling technique so that variables can have comparable scale 
  4. Building a linear model
      - Linear model was build using statsmodels 
      - Started with 10 variables using sklearn RFE technique and dropped variables having high (>5) Variance Inflation Factor (VIF) and high p (>0.05) one by one after checking p and VIF everytime.
      - Dropped variables having coefficient of very low magnitude one by one after checking p, VIF and Adjusted R2 once variables having high VIF and high p value were cleaned up
      - Final model had R2 as 81% and Durbin-Watson as 1.999
  5. Resudual analysis of the training data
      - Applied model validated on training dataset
      - Residual analysis done to validate residuals are normally distributed with mean at 0
      - Checked y_predict vs y based on the training database to validate linear distribution (homoscedasticity) between the two 
  6. Making prediction using final model
      - Final model applied on test dataset
  7. Model evaluation
      - Model is evaluated based on test data using sklearn r2_score which gave R2 value which is within 5% of R2 generated based on training dataset
      - Checked y_predict vs y based on the test database to validate linear distribution (homoscedasticity) between the two
      - Did residual analysis on test dataset to validate residuals are normally distributed with mean at 0
  8. Summary
      - Created final linear regression equation and understood the impact of the drivers on bike sharing revenue 


   
 

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions
 -  Increase in temp causes an increase in bike rent when all other predictors are not changing
 -  Bike rent increases with increase in year when all other predictors are not changing
-   Increase in Light Snow/Light Rain + Thunderstorm + Scattered clouds/Light Rain + Scattered clouds causes a decrease in bike rent when all other predictors are not changing
-   Increase in windspeed causes a decrease in bike rent when all other predictors not not changing
-   During spring, there is a decrease in bike rent when all other predictor is not changing
-   During Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, there is a decrease in bike rent when all other predictor is not changing

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used
- Python 3.0 (Python lib used - numpy, pandas, seaborn, matplotlib, sklearn, statsmodels)
- Jupyter notebook
- Exploratory Data Anlysis (EDA) Concept
- Linear regression (single and multiple) Concept
- Inferential Statistics Concept

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Acknowledgements

- IIIT Bangalore
- Upgrad 


## Contact
Created by alokkmukherji@gmail.com 


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
