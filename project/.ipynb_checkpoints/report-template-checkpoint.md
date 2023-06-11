# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Chong Cheng Yang, Lionel

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
I realise that without performing any data analysis/feature engineering, the resulting model did not performed as well as expected. I need to replace negative numbers with zeros.

### What was the top ranked model that performed?
The WeightedEnsemble_L3 model was my top ranked model that performed.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
I performed feature engineering and broke up the date into year, month, day and hours. I also transformed season and weather into categorical data types.

### How much better did your model preform after adding additional features and why do you think that is?
My model performed a lot better, and I attribute it to the feature engineering that was performed to the dataset.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
Hyperparameter tuning improved and deproved the model, depending on which metric was adjusted.

### If you were given more time with this dataset, where do you think you would spend more time?
I would do more research on the given dataset and spend more time researching on models hyperparameter, which can be used for this problem.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|default_vals|default_vals|default_vals|1.39920|
|add_features|default_vals|default_vals|default_vals|0.47165|
|hpo|num_leaves: lower=26, upper=66|dropout_prob: 0.0, 0.5|num_boost_round: 100|0.50893|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

![model_training_score.png](model_training_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

![model_testing_score.png](model_testing_score.png)

## Summary
In summary, I was able to apply the concepts that was taught to me across the various lectures, and better understand the overall process of a ML pipeline. I was also taught on the usage of various tools on AWS to speed up development of new models.
