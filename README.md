# Welcome to food delivery-analysis repository

## About

This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on a food delivery dataset from [Kaggle](https://www.kaggle.com/datasets/gauravmalik26/food-delivery-dataset/data). For detailed walkthrough, please view the source code in order from:

1. [Data Extraction] <https://github.com/JasmineTye/food-delivery-analysis/blob/main/1.%20Data%20Extraction.ipynb>
2. [Data_Visualization] <https://github.com/JasmineTye/food-delivery-analysis/blob/main/2.%20Data_Visualization.ipynb>
3. [Machine_Learning] <https://github.com/JasmineTye/food-delivery-analysis/blob/main/3.%20Machine_Learning.ipynb>
4. [Conclusion_Product] <https://github.com/JasmineTye/food-delivery-analysis/blob/main/4.%20Conclusion_Product.ipynb>
5. [Compiled_Version] <https://github.com/JasmineTye/food-delivery-analysis/blob/main/5.%20Compiled%20Version.ipynb>
   
## Contributors
- Keng Jia Chi (@JiachiK) - Data Extraction, Data Visualization, Machine Learning, Conclusion_Product, Slides, Video Presentation
- Jasmine Tye (@JasmineTye) - Data Extraction, Data Visualization, Machine Learning, Conclusion_Product, Slides, Video Presentation
- Lee Qi Yuan (@zikchg) - Data Extraction, Data Visualization, Conclusion_Product, Slides, Video Presentation

## Problem Definition
- How can we predict time taken for delivery accurately and precisely?
- Which model would be the best to predict it?

## Models Used
1. Random Forest Regressor
2. XGBoost Regressor
3. LightGBM Regressor
4. Support Vector Regression
5. Ensemble-Model (Combination of above 4 models)

## Data Extraction
- Import data from foodDeliveryData.csv file obtained from Kaggle
- 20 columns of numerical and categorical data such as Weatherconditions, Vehicle_condition, Delivery_Person_Age, Delivery_Person_Rating 
- Number of rows before cleaning: 45593
- Data cleaning by removing rows with NaN values in any of the columns.
- Number of rows after cleaning: 41368
- Data preparation process:
  a) removing redundant data such as ID
  b) reclassifying some rows in dataset:
   - removing (min) from `Time_taken(min)`
   - removing (conditions) from `Weatherconditions`
   - changing value 'jam' to 'very high' in `road_traffic_density`
   - calculating distance of restaurant and delivery location and storing in `Distance_between_restaurant_and_delivery_place(KM)`
  c) ensuring all columns have the correct data type such as integer or float, instead of representing it as a string

## Data Visualisation
- In this section, we explore food delivery dataset through various visualisations to gain insights and understand the relationships between different variables.
- Libraries such as matplotlib and seaborn was used.
- Count plots revealed insightful data such as the most and least common categories for each variable.
- Box plots were plot for each variable against time taken to help detect outliers and identify relationships. Thus, helping to detect patterns and trends.
- Use Heatmap Association, Random Forest Regressor and Cramer's V to detect the top 3 categorical and numerical factors to aid in model training.

## Machine Learning
- Train the 5 models to accurately predict `Time_taken (min)`
- Models are analysed using R-squared value and Mean-squared error (MSE)
- From R-squared value and MSE, LightGBM model has the highest R-squared and lowest MSE
- Attempting to improve accuracy of LightGBM model, Optuna library was used for hyperparameter tuning for LightGBM model. However, it is noted that the untuned LightGBM was overall more accurate than the tuned model.
- K-fold cross validation was carried out to further evaluate the accuracies of each model
- Lastly, feature importance graph was plotted for each variable in LightGBM model and it was found that `Deliver_person_Age` was the top factor contributing to `Time_taken (min)` 

## Conclusion/ Recommendations
- Identified the top 3 numerical and categorical factors that significantly impact the food delivery time 
- LightGBM model is the most optimal and can be used to predict the time taken for delivery
- Recommendation: Swift Deliver application utilizes user-inputted values for top categorical and numerical factors to predict delivery time accurately using a LightGBM model trained on historical data, enhancing delivery process efficiency and customer satisfaction.
<img width="343" alt="image" src="https://github.com/JasmineTye/food-delivery-analysis/assets/82916679/6d1683d4-52ee-438c-ab97-940d38825fca">

 ## Future Improvement
- Incorporate deep neural networks machine learning techniques.
- Ensure that the model is robust and scalable to handle large volumes of data and real-time prediction requests, especially if it's deployed in a production environment.
- Integrate additionals features that could potentially impact delivery time to allow better prediction of time taken(more accurate).
- Incorporate a feedback mechanism where the actual delivery times are collected and used to update the model periodically, ensuring it remains accurate and reflective of real-world conditions.

## What did we learn from this project?
- Additional models such as Random Forest Regressor, LightGBM, XGBoost, and Support Vector Regression
- Optuna model to bettwe visualise and tune machine learning models
- Handling large data sets (~45k rows of data)
- One-hot encoding's necessity for categorical data and its methods of implementation

## References
- <https://optuna.org/#code_examples>
- <https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVR.html>
- <https://lightgbm.readthedocs.io/en/latest/pythonapi/lightgbm.LGBMRegressor.html>
- <https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html>
- <https://xgboost.readthedocs.io/en/stable/get_started.html>
- <https://www.statology.org/interpret-cramers-v/>
