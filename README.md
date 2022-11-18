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

<img width="451" alt="image" src="https://user-images.githubusercontent.com/106691255/202591802-4c69752f-1607-455e-9488-20d1df4beb2b.png">

<img width="370" alt="image" src="https://user-images.githubusercontent.com/106691255/202591826-547e9457-25b2-4d9b-b3fc-60e50adb7e7d.png">

<img width="713" alt="image" src="https://user-images.githubusercontent.com/106691255/202591854-a5e87d43-2a91-4193-b434-f7fd1f9e216a.png">

##### SMOTE: Balanced Accuracy Score: 64%, Precision Predicting High Risk: 1%

SMOTE stands for Synthetic Minority Over-sampling Technique.

<img width="355" alt="image" src="https://user-images.githubusercontent.com/106691255/202591910-961ab604-2d63-46ef-a439-fcc662a6c185.png">

<img width="367" alt="image" src="https://user-images.githubusercontent.com/106691255/202591937-739999fb-7fdb-465f-b297-d3b153b519ce.png">

<img width="707" alt="image" src="https://user-images.githubusercontent.com/106691255/202591960-8051044e-b72f-44f1-8543-e59ca86ed95b.png">

#### Undersampling:

##### ClusterCentroids: Balanced Accuracy Score: 54%, Precision Predicting High Risk: 1%

This method is an undersampling that works by generating centroids based on clustering methods. It under samples the majority class by replacing a cluster of majority samples by the cluster centroid of a KMeans algorithm. This algorithm keeps N majority samples by fitting the KMeans algorithm with N cluster to the majority class and using the coordinates of the N cluster centroids as the new majority samples.

<img width="371" alt="image" src="https://user-images.githubusercontent.com/106691255/202592005-837b67ef-edea-419b-a3f6-8a5b0485336f.png">

<img width="379" alt="image" src="https://user-images.githubusercontent.com/106691255/202592063-ffdbd988-ddec-4eff-8873-e97dbcbf4235.png">

<img width="714" alt="image" src="https://user-images.githubusercontent.com/106691255/202592086-579a128e-70c9-40b7-b2dc-ed3b9d490769.png">

### Using the SMOTEENN algorithm to Predict Credit Risk: Balanced Accuracy Score: 64%, Precision Predicting High Risk: 1%

SMOTEEN is an over-sampling method using SMOTE and cleaning using ENN. It combines over- and under-sampling using SMOTE and Edited Nearest Neighbours.

<img width="356" alt="image" src="https://user-images.githubusercontent.com/106691255/202592141-fc7fb502-9238-480d-96ca-eaf75fa0b3e5.png">

<img width="381" alt="image" src="https://user-images.githubusercontent.com/106691255/202592175-ce78fb7e-af8f-4e7c-b06e-b225236bdc70.png">

<img width="720" alt="image" src="https://user-images.githubusercontent.com/106691255/202592197-80f55d9b-1b10-4154-9902-df593253cc0f.png">

### Using Ensemble Classifiers to Predict Credit Risk: 

Two different Machine Learning models were employed in an attempt to reduce the bias. 

#### BalancedRandomForestClassifier: Balanced Accuracy Score: 78%, Precision Predicting High Risk: 3%

This is an ensemble method in which each tree of the forest will be provided a bootstrap sample in order to balance it.

<img width="360" alt="image" src="https://user-images.githubusercontent.com/106691255/202591297-0ffae4f7-3f80-4d8e-9ce5-c6cc9c644e89.png">

<img width="367" alt="image" src="https://user-images.githubusercontent.com/106691255/202591325-c2979caf-5f6f-4607-8493-db5e84cd0ed3.png">

<img width="711" alt="image" src="https://user-images.githubusercontent.com/106691255/202591605-784bc78e-835d-4c5e-a7a6-349a843ffe67.png">

#### EasyEnsembleClassifier: Balanced Accuracy Score: 93%, Precision Predicting High Risk: 9%

This classifier is an ensemble of AdaBoost learners trained on different balanced boostrap samples. The balancing is achieved by random under-sampling.

<img width="358" alt="image" src="https://user-images.githubusercontent.com/106691255/202591668-90dc0172-c0cc-4cb5-b5e2-b126537d6e1e.png">

<img width="371" alt="image" src="https://user-images.githubusercontent.com/106691255/202591690-309b9307-fd1b-490d-81f2-06b306a6b35c.png">

<img width="717" alt="image" src="https://user-images.githubusercontent.com/106691255/202591719-e3592937-8cc5-4db8-aba8-d95ccf654b72.png">

## Summary

There are many different machine learning models that can be employed on data sets. It is important to find the one that presents the best results with the least bias for any particular data set.

In this case, the EasyEnsembleClassifier yielded the best results. I would recommend it for use with this data set. It had a balanced accuracy score of 93% and a 9% precision rate in predicting the "high risk" potential borrowers. The recall/sensitivity rate was 92% in predicting "high risk" and 94% in predicting "low risk". The overall f1 score was 97%.
