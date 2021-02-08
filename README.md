# Supervised Machine Learning Project 
## Overview
For this assignment the task was to create a variety of different ML models to predict credit risk. Because credit risk is inherently unbalanced (there are substantially more good loans than risky ones) I employed different techniques to train and evaluate models with unbalanced classes. I created these models in Python and used imbalanced-learn and sci-kit libraries to build and evaluate the models. Lastly, I made an educated recommendation on whether these models were an accurate or precise enough means for prediction credit risk. 
## Data
The ML models in this assignment used data from a peer-to-peer lending services company called LendingClub. The file is located in the Resources folder in the Module_17_Challenge. The file is a CSV called LoanStats_2019Q1.csv
## Contents
Folder | Description
-------|------------
Machine_Learning_Examples | Contains notebooks and data used in Module's ML examples 
Module_17_Challenge | Contains final assignment notebook and data file
## Resampling Techniques
1. Naive Random Oversampling
2. Synthetic minority Oversampling Technique (SMOTE)
3. Undersampling
4. Combination Sampling (SMOTEEN)

## Naive Random Oversampling
In random oversampling, instances of the minority class are randomly selected and added to the training set until the majority and minorty classes are balanced. 
Confusion matrix and Classification Report:
![alt-text](https://github.com/Abigail-Woolf/Supervised_Machine_Learning/blob/main/Images/Naive_Rand_Oversampling.png)

## SMOTE Oversampling
Similar to Random Oversampling, instances of the minority class are increased in size. Instead of randomly selecting instances from the minorty class to be increased however, SMOTE interpolates new instances of the minority class based on a number of its closest neighbors. 

## Undersampling
Undersampling involved decreasing the size of the minority class and I focused on the types: random and cluster centroid undersampling. 
In Random Undersampling, selected instances from the majoprity class are removed until the size of the majority class is reduced. Typically, it is reduced to the size of the minority class. 
In Cluster Centroid Undersampling, the algorithm identifies clusters of the majority class, generates synthetic data points, called centroids, that are representative of the clusters. The majority class is then undersampled down to the size of the minority class. (Similar to SMOTE)

## Combination Sampling (SMOTEEN)
SMOTEEN is a comnination of SMOTE and Edited Nearest Neighbors (ENN) algorithms. It is a two step process:
1. Oversample the minority class with SMOTE.
2. Clean the resulting data by undersampling. When the two nearest neighbors of a data point belong to two different classes, the data point is dropped. 

## Accuracy Scores, Confusion Matrix, and Final Analysis
An accuracy score is used to determine the performance of a machine learning model. Accuracy Scores are most accurate when evaluating models with continuous, not discrete, target variables.

In this module, we are looking into different ways to classify the outcome into one of two discrete variables. The accuracy score of the Random Oversampling technique was 71.14%. The confusion matrix looks like the model classifies things correctly, more than it classifies things incorrectly. That is consistent with the accuracy score. 
-
Another measure to check is the precision of the model, also known as, positive predictive value (true positives/(true positives + false positives)). Precision is how realible a positive classification is.
-
One more way to assess a model's performance is with recall, which is another name for sensitivity. Sensitivity = true positive/(true positive + false negative)). There is a correlation between recall and precision, and there needs to be a balance between the two for a model to perform optimally. The value that represents the optimal combination of recall and precision is called the F1 score. It ranges from 0 to 1, with 1 being the best (or most best performer). 
-
Based on these factors the model I would choose to be the best performer is the naive random sampling model. The accuracy score was about 71% while the F1 score was 0.02. As a matter of fact, each model had an F1 score of 0.02. 
-
For the ensemble classifiers, the easy ensemble adaboost performed better than the balanced random forest classifier. The accuracy score for this better model was about 91% with an F1 score of 0.16. Compared to all the other models I ran in this module, this one performed substantially better than the rest. 
