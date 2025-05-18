# Introduction and Summary

In this work I will evaluate and rank a number of ML models to analyze and predict the disease given
some health markers in patients. The work includes data visualization to establish correlation of
features to outcome and also determine if data has outiers or any other problems that require special
treatment. 

## Overview

+ Main Product
+ Data Visualization
+ Data Cleanup
+ Visualization After Data Cleanup
+ Is Data Balanced
+ Metrics Used For Evaluation of Models
+ Test and Train Split
+ First Level Model Exploration
+ Summary Of Baseline Results
+ Hyper Parameter Exploration
+ Voting Classifier Based on Our Best Models
+ Feature Importance Study: Best 'recall' models
+ Polynomial Feature Investigation

## Main Product

The main outcome of this work is an ML model that can be used to do early prediction of disease
on patients given some health markers and medical history.

## Data Visualization

For this stage I had tow goals which were determine high correlation betwen features and outcomes and 
searching for outliers to be eliminated in the next stage. Both of these were achived: in features that
are highly correlated to the outcome you can see clear separation and you can also see features with
outliers clearly separated from the main group.

## Data Cleanup

In this stage outlier points were eliminated as they did not significantly reduced the size of the
original data.

## Visualization After Data Cleanup

In this stage I made sure that visualization of the features that had outliers shows the cleanup was 
successfully performed.

## Is Data Balanced

Here I checked that data had some acceptable balance as this may have some influence in the metric used.
In this case we were borderline into what could be considered a balanced data set so I did not employ
techniques like SMOTES.

## Metrics Used For Evaluation of Models

In this section I justify the use of recall as my main metric to evaluate models for my specific application.

## Test and Train Split

Here I just perform a traditional 80-20 train test split to evaluate our models. I also use the standard scaler 
on features as it does helps in many models and does not negatively impat others like decision trees.

## First Level Model Exploration

The following models are examined here with some minor parameter exploration in one single dimension to get a
better understanding of the model:
+ Decision Trees
+ SVC
+ Gradient Boos Classifier
+ Random Forest Classifier
+ Logistic Regression
+ KNN Classifier
+ MLP Classifier
+ Keras Sequntial Neural Network

## Summary Of Baseline Results

Baseline model exploration with one dimensional hyper parameter exploration gives SVC, Decision Trees and Keras 
Sequential Model as our top classifiers with corresponding recall scores of 0.69, 0.65, and 0.63. Note that all
these models are computational intensive and slower than the other ones.

## Hyper Parameter Exploration

In this stage I used GridSearchCV with cv set to 5 to explore the hyperparameter space for all of these models except for 
Keras Sequential NN, for which I would have needed to design different code to explore and ran out of time. For this
stage I had to move to Colab as it was too computationally intensive for my aging laptop to handle in resonable time,
and even in Colab I had to split the parameter exploration in stages not to be charged and for them to complete in less 
than an hour. On this first part I sort models based on accuracy and then based on recall.
Best models based on recall is SVC with metric recall with test recall score of 0.69, followed with decision tree
classifier with a recall score of 0.65. This is similar to what I obtained in the baseline stage and this is likely
due to the fact that I had done some initial one dimansional hyperparameter search.

## Voting Classifier Based on Our Best Models

For this stage I selected my best clasifiers and used them to create a voting classifier to see if I could improve on 
the top ones. The aggregate recall score of 0.63 was among the top ones for our baseline exploration but yet below our
top model SVC with recall of 0.69

## Feature Importance Study: Best 'recall' models

For this stage I compute the feature imprtance for our best models and normalize their feature imprtance so we can
compare on a visualization chart. As expected from initial visualization of correlation Glucose and BMI come up
as most correlated to positive outcome. Age and DiabetesPedigree are in the second set of medium correlated factors.
From the plot in this section the least correlated factor seems skinthickness.


## Feature Importance: Wisdom of the Crowd Feature Importance

On this section I try to emulate the logic of voting classifiers to rank the feature importance based on all models
and the order of importance makes a lot of sense: Glucose, BMI, Age, DiabetesPedigree, Insulin are top factors.


## Polynomial Feature Investigation

Finally, in this section I set to explore whether a polynomial feature of degree 3 can expand our model score due to 
some non linear dependencies in our outcome, although I think that would have already been handled by MLP as we learned
in the leactures.

From the result tables I see that our top recall score still under our top model SVC: our top model with degree 3 polynomial
features is logistic regression with recall score of 0.65.

In conclusion our best model here is SVC with recall metric of 0.69. We can likely improve that with larger data set or a
more balanced one.

