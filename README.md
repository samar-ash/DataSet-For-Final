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
![image](https://user-images.githubusercontent.com/15922299/232816582-3e0111ba-1a75-42fa-b66a-793c2344675f.png)


## And finally we try to see outliers:
![image](https://user-images.githubusercontent.com/15922299/232823577-9e1ff988-950f-4c50-bbb6-f20fa01d649a.png)

   

## Preprocessing/ Exploration with the Data
There is NA for some records that does not mean it is an empty record. Forexample in the picture below, it means there is no access to the alley. However, all of them converted to Nan values automatically. So as a first step, I replaced those NA, with NOT.
![image](https://user-images.githubusercontent.com/15922299/232824585-caaf58ec-915b-4f06-be83-07232eb7f94f.png)
![image](https://user-images.githubusercontent.com/15922299/232825381-4dd8207f-8b98-48e6-adf8-f3007a4a1ebf.png)


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


