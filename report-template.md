# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Hudson Barroso Lucas

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
I realized I cannot to submit negative values in order to not be rejected by kaglle, because the evaluation calculation is RMSLE.
So it was necessary changing all negative values to 0

### What was the top ranked model that performed?
The top model was: WeightedEnsemble_L3

model                 score_val      pred_time_val  fit_time     pred_time_val_marginal    fit_time_marginal stack_level   can_infer  fit_order
WeightedEnsemble_L3  -52.845886      11.313885      508.325923   0.000796                  0.349383          3             True       15

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?

During the exploratory analysis I realized that:

People prefer the weather 1 (Clear Days)
The time they generally use is around 5pm and 7pm, and 8AM
There is not strong correlations according to heatmap, the higher was 0.39 Count x Temp 

The way to add aditional features was:
Use datetime to extract: Year, Month, Day and Hour

### How much better did your model preform after adding additional features and why do you think that is?
The model performed much better, from 1.81359 to 0.46343
The new feature Hour can explain much better the count target
Also I believe the correct feature type change

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
After hyper parameter change the model increased a bit, from 0.45311 to 0.45260
Maybe it can improve if I test more conditions and hyperparameters combinations

### If you were given more time with this dataset, where do you think you would spend more time?
For sure I should spend more time in exploratory analysis to understand better the data 
Create more features, test a lot and make experimentations with different combinations of Hyper Parameters
It's important to understand that I cannot exaust tuning the model withou good data and features! 

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.

|model|time|num_bag_folds|num_stack_levels|score|
|--|--|--|--|--|
|initial|600|8|3|1.81359|
|add_features|900|8|3|0.46343|
|hpo|1200|5|1|0.46182|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](https://c2-ml-torkflow-training.s3.amazonaws.com/l2e1/challenge/model_train_score.png)


### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](https://c2-ml-torkflow-training.s3.amazonaws.com/l2e1/challenge/model_test_score.png)

## Summary
This project shows how powerful is autogluon,
We can proceed with some exploratory analysis to better understand the dataset and apply some of the skills we learned previously
The finals scores improved from 1.81359 RMSLE to 0.45260 RMSLE and it's not a bad score in the kaggle competition 
The final score can be also improved with some feature engenieer and model tuning
