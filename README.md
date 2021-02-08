# Supervised Machine Learning Project 
## Overview
For this assignment the task was to create a variety of different ML models to predict credit risk. Because credit risk is inherently unbalanced (there are substantially more good loans than risky ones) I employed different techniques to train and evaluate models with unbalanced classes. I created these models in Python and used imbalanced-learn and sci-kit libraries to build and evaluate the models. Lastly, I made an educated recommendation on whether these models were an accurate or precise enough means for prediction credit risk. 
## Data
The ML models in this assignment used data from a peer-to-peer lending services company called LendingClub. The file is located in the Resources folder the Module_17_Challenge. The file is a CSV called LoanStats_2019Q1.csv
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
Accuracy_Score = 0.711

Classification Report:
![alt-text](https://github.com/Abigail-Woolf/Supervised_Machine_Learning/blob/main/Images/Rand_OverSamp_Classif_Report.png)

## SMOTE Oversampling
Similar to Random Oversampling, instances of the minority class are increased in size. Instead of randomly selecting instances from the minorty class to be increased however, SMOTE interpolates new instances of the minority class based on a number of its closest neighbors. 
Accuracy_Score = 0.708

Classification Report:
![alt-text](https://github.com/Abigail-Woolf/Supervised_Machine_Learning/blob/main/Images/SMOTE_Classif_Report.png)

## Undersampling
Undersampling involved decreasing the size of the minority class and I focused on the types: random and cluster centroid undersampling. 
In Random Undersampling, selected instances from the majoprity class are removed until the size of the majority class is reduced. Typically, it is reduced to the size of the minority class. 
In Cluster Centroid Undersampling, the algorithm identifies clusters of the majority class, generates synthetic data points, called centroids, that are representative of the clusters. The majority class is then undersampled down to the size of the minority class. (Similar to SMOTE)
Accuracy_Score = 0.695

Classification Report:
![alt-text](https://github.com/Abigail-Woolf/Supervised_Machine_Learning/blob/main/Images/Undersample_Classif_Report.png)

## Combination Sampling (SMOTEEN)
SMOTEEN is a comnination of SMOTE and Edited Nearest Neighbors (ENN) algorithms. It is a two step process:
1. Oversample the minority class with SMOTE.
2. Clean the resulting data by undersampling. When the two nearest neighbors of a data point belong to two different classes, the data point is dropped. 
Accuracy_Score = 0.721

Classification Report:
![alt-text](https://github.com/Abigail-Woolf/Supervised_Machine_Learning/blob/main/Images/SMOTEEN_Classif_Report.png)

## Final Analysis
Based on the accuracy scores and classification reports all resampling techniques performed about the same. They all had F1 scores of 0.02 except for SMOTEEN which had 0.03 and all had accuracy scores oscillating around 0.70. 

Another task completed in this module was implementing two (new to me) ensemble classifiers, easy ensemble Adaboost and balanced random forest, to predict loan risk and evaluate each of the models. 
For the ensemble classifiers, the easy ensemble adaboost performed better than the balanced random forest classifier with an accuracy score of 0.93 and an F1 score of 0.16. The balanced random forest has an accuracy score of 0.75 and an F1 score of 0.05, making adaboost the obvious winner. 
