# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### NAME HERE
Denis Tsvetanov
## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
No initial changes were needed in order to submit the results. The predictor was fit on the data and provided a reasonable although not excellent rmse score.

### What was the top ranked model that performed?
WeightedEnsemble_L3

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
There were several columns that could be used in feature extraction. No one-hot encoding was done, altough there are columns to accomodate such changes.
Additional columns were extracted from the datetime in order to find more granular dependencies between the end result and the processes in the features.

### How much better did your model preform after adding additional features and why do you think that is?
Reduced the rmse by half. Some of the newly created columns is a strong predictor for the target, which wasn't visible with the data coupled in a single feature.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
Didn't do much better, actually did a bit worse.

### If you were given more time with this dataset, where do you think you would spend more time?
I would go into detail with fine-tuning the *kwargs and models used, since currently the ones I have handpicked didn't do as well as the auto ones of autogluon.
Additional feature engineering might prove beneficial too.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model       |hpo1 |hpo2|hpo3|score  |
|--          |--   |--  |--  |--     |
|initial     |False|None|None|1.80419|
|add_features|False|None|None|0.69552|
|hpo         |True | 5  | 2  |0.70198|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)

## Summary
Overall autogluon exceeded my expectations and provided a good model with an acceptable rmse score out of the bat, most notable help to the autogluon algorithms is the feature engineering done before feeding the data into the system which made the model even more accurate. Certainly insights can be gained on what model to use and it is far quicker than GridSearchCV when working with hyperparams .
