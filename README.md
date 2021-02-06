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

An accuracy score is used to determine the performance of a machine learning model. It works best and most accurately when evaluationg models with continuous target variables. That being said, I think that the accuracy score is not the best test to determine the performance of the models in Module 17. In this module, we are looking into different ways to classify the outcome into one of two discrete variables. The accuracy score of the Random Oversampling technique was 71.14%. The confusion matrix looks like the model classifies things correctly, more than it classifies things incorrectly. That is consistent with the accuracy score. 
-
Another measure to check is the precision of the model, also known as, positive predictive value (true positives/(true positives + false positives)). Precision is how realible a positive classification is.
-
One more way to assess a model's performance is with recall, which is another name for sensitivity. Sensitivity = true positive/(true positive + false negative)). There is a correlation between recall and precision, and there needs to be a balance between the two for a model to perform optimally. The value that represents the optimal combination of recall and precision is called the F1 score. It ranges from 0 to 1, with 1 being the best (or most best performer). 
-
Based on these factors the model I would choose to be the best performer is the naive random sampling model. The accuracy score was about 71% while the F1 score was 0.02. As a matter of fact, each model had an F1 score of 0.02. 
-
For the ensemble classifiers, the easy ensemble adaboost performed better than the balanced random forest classifier. The accuracy score for this better model was about 91% with an F1 score of 0.16. Compared to all the other models I ran in this module, this one performed substantially better than the rest. 
