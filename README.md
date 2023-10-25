# House Price Prediction Case Study 

A US-based housing company named "Surprise Housing" uses data analytics to purchase houses at a price below their actual values and flip them on at a higher price. It has decided to enter the Australian market and so it is looking at prospective properties to buy to enter the market. 

For this purpose, the company wants to know :
1. Which factors are significant in predicting the price of a house
2. How well those factors describe the price of a house.
   
Business Objective:

To understand how exactly the SalePrice vary with the features so that this knowledge can be used to concentrate on areas that will yield high returns
To understand the pricing dynamics of a new market.


## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

## General Information
- To create a regression model for the target variable named "SalePrice" based on collected data set and using regularisation technique in order to predict the actual value of the prospective properties accurately so that it can be decided whether it will be good to invest in those or not.
- Steps followed for this analysis: 
  1. Reading and cleaning the Data
     - Input dataset used for this analysis had 1460 rows and 81 columns
     - The data cleaning step included
        1. Handling missing data
        2. Converting integer values to corresponding categorical values 
        3. Handling columns having most of the elements as zero
        4. Removing columns which are not required for analysis
  2. Visualising the data and EDA  - 
     -  Created different plots to understand the relationship (specifically to understand linear relationship) between different sets of variables 
  3. Data preparation for Modeling
        1. Converting categorical variables to dummy variables - so that they become suitable for model building 
        2. Splitting data into Training and Test sets at 70% (for training data) and 30% (for evaluating data) ratio respectively
        3. Rescaling features using Min-Max scaling technique so that variables can have comparable scale 
  4. Building a linear model (w/o regularization)
      - Linear model was built using scikit learn and R2 was checked. Found issue related to overfitting
  5. Building linear models using Lasso and Ridge regularization techniques to overcome overfitting
      - Model evaluation
           - Evaluated model based on R2 and RMSE
           - Checked y_predict vs y based on the test database to validate linear distribution (homoscedasticity) between the two
           - Did residual analysis on test dataset to validate residuals are normally distributed with mean at 0
  6. Comparitative study of Lasso and Ridge result
      - R2
      - RMSE
      - No. of non zero coefficients
  8. Conclusion/Summary
      - Which regularization technique is good
      - FInal set of predictors which have more influence on "SaleProce"

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions
- r2 score value comparison (Train set)
  - r2_score_train_ridge: 0.8725628328133331
  - r2_score_train_lasso: 0.8621306864920301
- r2 score value comparison (Test set)
  - r2_score_test_ridge: 0.8337465365920929
  - r2_score_test_lasso: 0.8308600747150239
- RMSE comparison
  - Ridge: 0.053800308331706785
  - Lasso: 0.054265334094987634
- The optimal alpha value in case of Ridge and Lasso is as below:
  - Ridge : 50
  - Lasso : 0.001
- No.of coefficients of the features greater than 0:
  - Ridge : 240
  - Lasso : 52
  So, Lasso is able to reduce the no of insifnificant features significantly compared to Ridge maintaining similar accuracy

- Based on Lasso, the features mentioned below will affect "SalePrice" mostly:
  - GrLivArea
  - GarageCars
  - OverallQual_EXCELLENT
  - TotRmsAbvGrd
  - YearRemodAdd
  - OverallQual_VERY_GOOD
  - CentralAir_Y
  - BsmtExposure_Gd
  - FireplaceQu_No Fireplace (-ve correlation with 'SalePrice')
  - FullBath
  - MSSubClass_ONE_STORY_1945_AND_OLDER (-ve corelation with 'SalePrice')
​
<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used
- Python 3.0 (Python lib used - numpy, pandas, seaborn, matplotlib, sklearn, Lasso, Ridge)
- Jupyter notebook
- Exploratory Data Anlysis (EDA) Concept
- Linear regression and regularization Concept
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
