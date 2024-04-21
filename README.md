# Welcome to food delivery-analysis repository

## About

This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on a food delivery dataset from [Kaggle](https://www.kaggle.com/datasets/gauravmalik26/food-delivery-dataset/data). For detailed walkthrough, please view the source code in order from:

1. [Data Extraction]
2. [Explanatory Data Analysis]
3. [Model Training]
  
## Contributors
Keng Jia Chi ()
Jasmine Tye Jia Wen (jtye002@e.ntu.edu.sg)
Lee Qi Yuan ()

## Problem Definition
- How can we predict time taken for delivery accurately and precisely?
- Which model would be the best to predict it?

## Models Used

1. Random Forest Regressor
2. XGBoost Regressor
3. LightGBM Regressor
4. Support Vector Regression

## Conclusion/ Recommendations
- Identified the top 3 numerical and categorical factors that significantly impact the food delivery time 
- LightGBM model is the most optimal and can be used to predict the time taken for delivery
- Recommendation: Swift Deliver application utilizes user-inputted values for top categorical and numerical factors to predict delivery time accurately using a LightGBM model trained on historical data, enhancing delivery process efficiency and customer satisfaction.
<img width="343" alt="image" src="https://github.com/JasmineTye/food-delivery-analysis/assets/82916679/6d1683d4-52ee-438c-ab97-940d38825fca">
 

## What did we learn from this project?
- Additional models such as Random Forest Regressor, LightGBM, XGBoost, and Support Vector Regression
- Optuna model to bettwe visualise and tune machine learning models
- Handling large data sets (~45k rows of data)
- 

## References
- <https://optuna.org/#code_examples>
- <https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVR.html>
- <https://lightgbm.readthedocs.io/en/latest/pythonapi/lightgbm.LGBMRegressor.html>
- <https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html>
- <https://xgboost.readthedocs.io/en/stable/get_started.html>
