# Credit_Risk_Analysis

## Overview of the analysis:

Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore, different techniques are needed to train and evaluate models with unbalanced classes. To tackle the unbalanced classes, I used imbalanced-learn and scikit-learn libraries, to build and evaluate models using resampling.

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, I've oversampled the data using the RandomOverSampler and SMOTE algorithms, and undersampled the data using the ClusterCentroids algorithm. Then, I used a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. Then, I compared two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk.

## Results:

### Credit Risk Resampling

#### Oversampling

![oversample](https://user-images.githubusercontent.com/102183530/182263424-3cd785e8-0e16-41a3-904f-a041998b8d90.png)

### SMOTE

![SMOTE](https://user-images.githubusercontent.com/102183530/182263443-763fe3b0-3f2f-4e0c-98e0-f3fb86e9214b.png)

### Undersampling

![Undersampling](https://user-images.githubusercontent.com/102183530/182263684-01425ba2-42a9-484b-bd9b-fd263b1d7f4d.png)

### Combination (Over & Under) Sampling

![ComboSampling](https://user-images.githubusercontent.com/102183530/182263699-6084ee22-c0e5-4eb5-9b22-72b1f1a40875.png)


Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all six machine learning models. Use screenshots of your outputs to support your results.

## Summary: 
Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning.
