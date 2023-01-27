# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### José Fernando Pérez Pérez

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
That the majority of the models doesn´t filter the negative outputs, in our case we can´t predict negative numbers of shared bikes so I need to apply a mask to filter all the negative predictions and replace it with zeros.

### What was the top ranked model that performed?
The best model that I found is: WeightedEnsemble_L2.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
Based on the histogram plots it was very difficult to see if a variable was directly correlated with the target, thanks to the clue provided about the date split I was able to split the datetime column into year, month, day and hour columns and for my surprise the hour seams to be correlated with the target.

### How much better did your model preform after adding additional features and why do you think that is?
100% better than the raw version, looking at the new histograms based on the additional features it appears that the hour column makes a huge impact on the target because they are correlated.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
Just a little improvement maybe adding some more parameters and different combinations the model could be better.

### If you were given more time with this dataset, where do you think you would spend more time?
First of all doing more EDA and trying to create more features and then take more time to hyperparameter tuning.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|default_vals|default_vals|default_vals|1.78777|
|add_features|default_vals|default_vals|default_vals|0.63932|
|hpo|GBM: num_leaves: lower=26, upper=66|NN: dropout_prob: 0.0, 0.5|XGB: num_estimators: lower=100, max=500|0.54163|

### Create a line plot showing the top model score for the three (or more) training runs during the project.


![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.


![model_test_score.png](img/model_test_score.png)

## Summary
With this project I was able to understand the importance of EDA and Hyperparameter tuning inside the ML workflow, also I had the opportunity to start learning on how to use AWS for ML. The whole project is amazing because I can understand the problem and the use of new tools for solving it.