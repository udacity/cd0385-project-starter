# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### AJAYI JOHN

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
Kaggle rejects negative score values, hence, the negative values was set to zero before submission

### What was the top ranked model that performed?
The top ranked model that performed is the "WeightedEnsemble_L3" with a score  of and RMSE value of -53.055. RMSE evaluation metric was used. Hence, the lower the error, the better the model.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
The temp and atemp features are almost perfectly skewed, indicating that the temperature range is almost the same all through the week. 
The causal users, windspeed, registered and count columns are left-skewed. This is an indicator that  do not have particular periods of the day to lend a bike.
The other columns are simply discrete values

### How much better did your model preform after adding additional features and why do you think that is?
After adding additional features, the model inproved significantly. This included also converting certain features to categorical variables.
From an initial RMSE value of -53 to RMSE value of -30.1837. Also, the kaggle score improved from 1.79030 to 0.67749

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
Tuning of some of the hyerparameters also improved the model's performace
Some of the hyperparameters that were tuned included the 'number of boost rounds', 'learning rate',  'num_leaves', 'max_depth'
The hyperparameter tuning moved the model from a previous RMSE value of -30 to -32.78335 though with a significant increase in the kaggle score wwhich went from 0.67749 to 0.44964. This is probably an indication of the required metric needed for evaluating the model.

### If you were given more time with this dataset, where do you think you would spend more time?
Given more time with this dataset, I would focus on how working more on the feature engineering and also on the hyperparameter tuning. These two tends to have a significant effect on the model's performance.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|CAT|XGB|GBM|RF|score|
|--|--|--|--|--|--|
|initial|default|default|default|default|1.79030|
|add_features|default|default|default|default|0.67749|
|hpo|'depth':8, 'l2_leaf_reg':10'|'objective':'reg:pseudohubererror', 'eval_metric':'rmse', 'max_depth':10, 'eta':0.03|'objective':'regression_l1', 'num_boost_round':500, 'num_leaves':50, 'eta':0.001, 'random_state'=32|'n_estimators':500, 'max_depth':8, 'min_samples_split':4, 'min_samples_leaf':3, 'max_features':'auto', 'random_state':32|0.44964|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](img/model_train_score.png)default

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)

## Summary
In conclussion, I was able to create a model that can be used to predict the number of persons that makes use of the bike-sharing service in each day of the week. This will help the organization make useful decision and planning, hence, aiding the smooth running of the business.