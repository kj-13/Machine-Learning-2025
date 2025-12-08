# Machine-Learning-2025

## Audience Decode

### Group Members:

- Zygimantas Kazlauskas (322271)
- Kottage Don Chiara (315161)
- Elvin Magaia (315431)
- Gabija Baltrunaite (314771)

## Introduction

## EDA

## Models 

Using the cleaned data we started bulding the models required ,the first is a predicitive model for user ratings and doing a user segmentaion analysis . The features (number of ratings , rating variability, and relese year) are combined with each movie's average rating. 


The dataset is then divided into two part (train-80% and test-20% ) then the test data (80%) was divided into two parts (training -75% and  validation-25%) then this was used to get a better analyisis of the data .
Training data(60% of the total dataset) : to train and fit the model
Validation data(20% of the total dataset) : to tune the dataset before the final check
Test data(20% of the total dataset):to report the final output in a unbiased form


We also standerdized all variables so it affects the regression evenly. The linear regression is trained,validated and retrained before being tested in the test data , and then tested on mean square error-mse() , root mean square error-rmse() , mean absolute error-mae() and r square-r^2() .The actual vs predicted test ratings graph was then plotted tp provide a visual representation .


Next we prep the data for the next two clustering models ,using five user activity features (total ratings,avrage ratings,rating standrad deviation,number of uniques movies watched and activity days) users are categorized.After standardization of the data , the optimal number of clusters to be used in the model is calculated using both the Elbow method (inertia) and Silhouette score .


After choosing five as the optimal number of clusters from the dataset , we perform KMeans clusting first:


Since KMeans is more focused on lower variance within clusters, the results of this is based more on behavioural types of the users .



## Comparison of Models
