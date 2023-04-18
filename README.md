# Dataset-For-final-project

https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data

# House Prediction 

-------------------------------------------------
## Data Description
A competition hosted by Kaggle
The train  and test data that is given contains 1460  observations containing 79 features including categorical, ordinal and numeric features .
![image](https://user-images.githubusercontent.com/15922299/232815125-204d895c-58e7-4f35-9fcc-4432ba3f7da4.png)

you can see data_description.txt file for more information about features.
![image](https://user-images.githubusercontent.com/15922299/232814240-3a0984e2-e82a-43ee-a3f2-163f0776dfda.png)

First, I started with some analyzation on dataset.
![image](https://user-images.githubusercontent.com/15922299/232814936-bfcd3161-3e36-4ffa-b6a3-4ed081bbfd29.png)
![image](https://user-images.githubusercontent.com/15922299/232815578-cc5236ae-66ff-450d-8561-2edac5da44c3.png)


   

## Preprocessing/ Exploration with the Data
We started 
No nan values were included in this dataset
We also converted Type to numerical data by using 

df.replace({'clicks': 0, 'carts': 1,'orders':2}, inplace=True)

<img src="sns_pairplot.jpg" alt="Alt text" title="Pair Plots of all Features">

## Modeling
4  different Machine Learning algorithms were used:
- Unsupervised
  - K-means Clustering
- Supervised
  - K-Nearest Neighbors
  - Logistic Regression
  - Decision Trees
 
Small samples were originally used so program would run quicker 
Models were then chosen based on accuracy score to compare between others

## Findings
After performing the models we've determined KNN was the best model because of its accuracy rate with the testing data.

We can probably receive a better model if we are able to manipulate existing features 

Due to the fact that the dataset was large we couldn’t properly include every data point but there might be ways to work with big data that we don’t know at the moment

### Information about the competition result: Coming Soon!

## Sources 
https://www.kaggle.com/competitions/otto-recommender-system/overview
https://www.kaggle.com/code/junjitakeshima/otto-easy-understanding-for-beginner-en


