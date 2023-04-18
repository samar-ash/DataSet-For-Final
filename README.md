# Dataset-For-final-project

https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data

# House Prediction 

-------------------------------------------------
## Data Description
A competition hosted by Kaggle
The train  and test data that is given contains 1460  observations containing 80 features including categorical, ordinal and numerical features .
![image](https://user-images.githubusercontent.com/15922299/232814240-3a0984e2-e82a-43ee-a3f2-163f0776dfda.png)

you can see data_description.txt file for more information about features.
![image](https://user-images.githubusercontent.com/15922299/232815125-204d895c-58e7-4f35-9fcc-4432ba3f7da4.png)

![image](https://user-images.githubusercontent.com/15922299/232814936-bfcd3161-3e36-4ffa-b6a3-4ed081bbfd29.png)


## let us take a look at how the house prices are distributed.

![image](https://user-images.githubusercontent.com/15922299/232815578-cc5236ae-66ff-450d-8561-2edac5da44c3.png)

![image](https://user-images.githubusercontent.com/15922299/232816311-203fd4da-d9bb-40c7-baf5-da9015a73386.png)

## Numerical data distribution

We will now take a look at how the numerical features are distributed. In order to do this, let us first list all the types of data from our dataset and select only the numerical ones.

![image](https://user-images.githubusercontent.com/15922299/232816408-1ec299c1-77af-4ef5-bc94-9f6a49910dd9.png)
![image](https://user-images.githubusercontent.com/15922299/232816443-392f01ad-e4b3-48e6-ac21-061074b141c3.png)

## Categorical data distribution

We will now take a look at how the categorical features are distributed. In order to do this, let us first list all the types of data from our dataset and select only the categorical ones.

![image](https://user-images.githubusercontent.com/15922299/232816496-69dec857-a6e0-4ff7-93d9-2061b0c23f62.png)
![image](https://user-images.githubusercontent.com/15922299/232816512-cc6259ce-4c73-4e59-8860-802f716a0cbf.png)



## And finally we try to see outliers:
![image](https://user-images.githubusercontent.com/15922299/232823577-9e1ff988-950f-4c50-bbb6-f20fa01d649a.png)

   

## Preprocessing/ Exploration with the Data

for the first step, I checked Nan values in the data:

![image](https://user-images.githubusercontent.com/15922299/232816582-3e0111ba-1a75-42fa-b66a-793c2344675f.png)

There is NA for some records that does not mean it is an empty record. Forexample in the picture below, it means there is no access to the alley. However, all of them converted to Nan values automatically. So as a first step, I replaced those NA, with NOT.

![image](https://user-images.githubusercontent.com/15922299/232824585-caaf58ec-915b-4f06-be83-07232eb7f94f.png)
![image](https://user-images.githubusercontent.com/15922299/232825381-4dd8207f-8b98-48e6-adf8-f3007a4a1ebf.png)

## Create a Transformer 
I created a transform function to categorical features to OneHotEncoder and ordinal features to OrdinalEncoder. Also to fill Empty values using SimpleImputer.

## Train-Test Split
## GridSearchCv Evaluation:
I used neg_mean_error for GridSearchCV evaluation
Scikit-learn considers by convention that a score follow the rule: 'higher values are better than lower values'. In this case a small MSE shows that your predictions are close to data so it follows the opposite rule. That's why sklearn consider the negative (actually opposite) MSE as score.
And MSE means minimum square error( y_real - y_predicted)
The R2 score is one of the performance evaluation measures for regression-based machine learning models. It is also known as the coefficient of determination. If you want to learn how to evaluate the performance of a machine learning model using the r squared score

## Model Evaluation
I used R2 Score and MSE and RMSE and MAE
MAE=The mean absolute error measures the average differences between predicted values and actual values
RMSE= Root Mean Squared Error (RMSE) is the square root of the mean squared error between the predicted and actual values.
in regression problems, the RMSE score is used as a metric to measure performance and the mean squared error (MSE) is used to evaluate the performance of a regression model.
R 2 (coefficient of determination) regression score function.Best possible score for R2 is 1.0 and it can be negative (because the model can be arbitrarily worse).

## The result of running Baseline gridsearch is as follows: 
![image](https://user-images.githubusercontent.com/15922299/232869657-1d3a062e-d99a-437d-a41c-268dc8dc1d13.png)

Based on the table,It seems GradientBoostingRegression did better than two other algorithms both for train and test.
## After Experiment 1:
The Ridge performs poorly both for train and test. However GradientBoostRegression performed very well for train and test.
Svm get better only for train data but worse for the test data.
![image](https://user-images.githubusercontent.com/15922299/232880635-45579b3f-4562-4260-b954-0004e3b51dc4.png)

## After Experiment 2(Polynomial Feature):
adding polynomial feature usually should gives us better training result( even sometime overfitting) and sometimes better result for test data depends on the nature of features.

It increased the training performance for Ridge significntly better, but the performance for test data gets significantly worse.
However, GriadientBoosting get much better result both for train and test dataset.
![image](https://user-images.githubusercontent.com/15922299/232914092-ecaa851b-b31e-4ebd-b06d-d6427ed690c7.png)


## After Experiment 3 PCA transformation (Experiment 3):
there is no significant change, and it gets the results just a little worse. But for SVM results was significantly worse.
![image](https://user-images.githubusercontent.com/15922299/232915559-8b970bd1-3e79-4abe-94de-b04ba96a7909.png)




## After Experiment 4 MinmaxScaling (Experiment 4):
MinMaxScaler rescales the data set such that all feature values are in the range [0, 1] as shown in the right panel below. However, this scaling compress all inliers in the narrow range [0, 0.005] for the transformed number of households.

It makes train data performance better for ridge but not for the test data. However it makes significantly increase in the performance of test data for GradientBoosting. And performance is geting worse for SVM

![image](https://user-images.githubusercontent.com/15922299/232897727-2f97a4a3-f0ca-487f-ae25-199ef6cf6d04.png)


## After Adding random feature 1 (Experiment 5)

From the results, it seems after adding random feature all the models performance get worse which seems logical because it is irrelevant feature
![image](https://user-images.githubusercontent.com/15922299/232874574-1f5c96cb-1f9c-4c8f-8686-db689bc04427.png)


After performing the models we've determined KNN was the best model because of its accuracy rate with the testing data.

We can probably receive a better model if we are able to manipulate existing features 

Due to the fact that the dataset was large we couldn’t properly include every data point but there might be ways to work with big data that we don’t know at the moment

## After Adding random feature 2 (Discrete feature) ((Experiment 5)

![image](https://user-images.githubusercontent.com/15922299/232901223-a699a684-9353-4c1b-9a6b-56edff30d4c8.png)

Ridge and SVM did not show any significant change. However GradientBoosting show slighlty better result.
![image](https://user-images.githubusercontent.com/15922299/232900686-aa07d95a-69fb-401f-903d-11b438cd7312.png)

## Pipeline with the Best:
The final pipeline I created, used the imputer instead of filling Nan value by my approach and also use MinMaxScalor for numerical features and OnehotEncoder for categorical data and also OrdinalEncoder for ordinal features and polynomial degree 2 , with GradientBoostingRegression. Here is the final result:

![image](https://user-images.githubusercontent.com/15922299/232902855-de4d9c3d-2d0d-4cb7-adb2-acdff0502d8d.png)

## Future Improvements:
If I had more time, I would test ensemble learning with voting to see if it could make it better.nd I should submit the competition to see the result on the real test dataset.






