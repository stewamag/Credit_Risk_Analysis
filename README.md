# Credit Risk Analysis
Applying machine learning to solve a real-world challenge: credit card risk. 

## Purpose of the Project:

Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore, you’ll need to employ different techniques to train and evaluate models with unbalanced classes. Jill asks you to use imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling. 

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, I oversampled the data using the RandomOverSampler and SMOTE algorithms, and undersampled the data using the ClusterCentroids algorithm. 

Then, I used a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. 

Next, I compared two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk.

Finally, I evaluated the performance of these models and come up with a recommendation on whether they should be used to predict credit risk.

## Results:

### Using Resampling Models to Predict Credit Risk:

#### Oversampling:

##### RandomOverSampler: Balanced Accuracy Score: 64%, Precision Predicting High Risk: 1%

This method over-samples the minority class(es) by picking samples at random with replacement.

##### SMOTE: Balanced Accuracy Score: 64%, Precision Predicting High Risk: 1%

SMOTE stands for Synthetic Minority Over-sampling Technique.

#### Undersampling:

##### ClusterCentroids: Balanced Accuracy Score: 54%, Precision Predicting High Risk: 1%

This method is an undersampling that works by generating centroids based on clustering methods. It under samples the majority class by replacing a cluster of majority samples by the cluster centroid of a KMeans algorithm. This algorithm keeps N majority samples by fitting the KMeans algorithm with N cluster to the majority class and using the coordinates of the N cluster centroids as the new majority samples.

### Using the SMOTEENN algorithm to Predict Credit Risk: Balanced Accuracy Score: 64%, Precision Predicting High Risk: 1%

SMOTEEN is an over-sampling method using SMOTE and cleaning using ENN. It combines over- and under-sampling using SMOTE and Edited Nearest Neighbours.

### Using Ensemble Classifiers to Predict Credit Risk: 

Two different Machine Learning models were employed in an attempt to reduce the bias. 

#### BalancedRandomForestClassifier: Balanced Accuracy Score: 78%, Precision Predicting High Risk: 3%

This is an ensemble method in which each tree of the forest will be provided a bootstrap sample in order to balance it.

#### EasyEnsembleClassifier: Balanced Accuracy Score: 93%, Precision Predicting High Risk: 9%

This classifier is an ensemble of AdaBoost learners trained on different balanced boostrap samples. The balancing is achieved by random under-sampling.

## Summary

There are many different machine learning models that can be employed on data sets. It is important to find the one that presents the best results with the least bias for any particular data set.

In this case, the EasyEnsembleClassifier yielded the best results. I would recommend it for use with this data set. It had a balanced accuracy score of 93% and a 9% precision rate in predicting the "high risk" potential borrowers. The recall/sensitivity rate was 92% in predicting "high risk" and 94% in predicting "low risk". The overall f1 score was 97%.