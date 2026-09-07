# E-commerce customer satisfaction prediction

# Overview of the project
This project builds a machine learning regression model to predict customer "satisfaction_score"(1-5 rating) based on e-commerce transaction data from kaggle.

## Project workflow
 1. Finding a large enough database that allows me to make a machine learning project on it.
 2. Data preprocessing
 - First i cleaned the high cardinality categorical features such as ('City','country', etc.) 
 - Applied one-hot encoding ('pd.get_dummies'), expanding the dataset to 129 features.
 - identified and removed data leakage caused by the 'satisfaction_level' column.
 3. data splitting
 - splitting the data into 80% training data(40k rows) and 20% testing (10k rows).
 - applied 'standardscaler' fitted strictly on training data to prevent data leakage.
 4. Model training
 - Built a LinearRegression baseline model using scikit-learn.
 - Built a Randomforest model to compare with the baseline
 



 # Baseline performance
 * MSE: 1.170541119281402
 * R2 Score: 0.42186304621587845

 # Key drivers for baseline
 * churn_risk_category_Very Low    1.785344
 * churn_risk_category_Low         1.040054
 * purchase_frequency_Rarely       0.738691
 * churn_risk_category_Medium      0.390482
 * return_count                    0.302396

 # Randomforest performance
 * Random Forest MSE: 0.9946089499999998
 * Random Forest R2 Score: 0.5087569508771892

 # Key Drivers for Randomforest
 * churn_risk_category_Very Low    0.223104
 * return_count                    0.087783
 * complaint_count                 0.085301
 * days_since_last_purchase        0.055148
 * churn_risk_category_Low         0.045066
 
 # Findings in comparision between Linear and RandomForest
 - Moving to Random Forest improved the R^2 score by ~8.7%, bringing the total explained variance up to 50.9% 
 - the decision trees captured complex feature interactions (such as return counts and complaint histories) that the     linear model missed.
 
 
 