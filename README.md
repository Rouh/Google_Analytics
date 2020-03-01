# Google_Analytics
Google Analytics Customer Revenue Prediction project in kaggle.com. Predict how much GStore customers will spend
**About the Model**

In this kernel, thanks to the [ML-Ensemble](http://ml-ensemble.com/), I used Super Learner algorithm with Python to predict the customer revenue through the Google Analytics data.
This Super Learner algorithm, consists on LinearRegression as a meta-model and LightGBM, XGBRegressor, and CatBoostRegressor as base-models.
Also, thanks to the pandas new updates (Version 1.0.0) specialy in resolving issues with “named aggregation”, I was able to make a transparent and well organized codes for this project.

**Solution Structure**

Based on the train and test files and dates, we are going to predict returning customers behavior after a given time interval. Let's get started with calculating time interval.
Based on the project specs:
1. train_v2.csv file contains user transactions from August 1st, 2016 to April 30th, 2018 (637 days).
2. test_v2.csv file contains user transactions from May 1st, 2018 to October 15th, 2018 (167 days).
3. Final goal is to predict revenue for each of the visitors for the timeframe of December 1st, 2018 to January 31st, 2019 (61 days).
4. The gap between #2 and #3 is 47 days.

Based on the #2, #3, and #4, in this project we are going to predict revenue of returning visitores of 61 days interval (A) which visited the site in previous 167 days interval (B) and gap between the A and B is 47 days.
We can split our train data out based on this pattern and train our model to get ready for final predictions.


**References**
* ML_Ensemble documents, Link: http://ml-ensemble.com/
* [How to Develop Super Learner Ensembles in Python](https://machinelearningmastery.com/super-learner-ensemble-in-python/), by [Jason Brownlee](https://machinelearningmastery.com/author/jasonb/) on December 11, 2019 in Python Machine Learning.
* Data generation script: [https://www.kaggle.com/qnkhuat/make-data-ready](https://www.kaggle.com/qnkhuat/make-data-ready)
* Stacking part is from this script: https://www.kaggle.com/ashishpatel26/updated-bayesian-lgbm-xgb-cat-fe-kfold-cv
* Reference scripts for selecting important features, dataset splitting patterns, and others: https://www.kaggle.com/kostoglot/winning-solution, https://www.kaggle.com/augustmarvel/base-model-v2-user-level-solution
