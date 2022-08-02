# Credit_Risk_Analysis

## Overview of the analysis:

Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore, different techniques are needed to train and evaluate models with unbalanced classes. To tackle the unbalanced classes, I used imbalanced-learn and scikit-learn libraries, to build and evaluate models using resampling.

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, I've oversampled the data using the RandomOverSampler and SMOTE algorithms, and undersampled the data using the ClusterCentroids algorithm. Then, I used a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. Then, I compared two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk.

## Results:

### Credit Risk Resampling

#### Oversampling

![oversample](https://user-images.githubusercontent.com/102183530/182263424-3cd785e8-0e16-41a3-904f-a041998b8d90.png)

-- The balanced accuracy score is 64%.
-- The high_risk precision is 1% only with 60% sensitivity which makes a F1 of 2%
-- Due to the high number of the low_risk population, its precision is 99% with a sensitivity of 68%.

### SMOTE

![SMOTE](https://user-images.githubusercontent.com/102183530/182263443-763fe3b0-3f2f-4e0c-98e0-f3fb86e9214b.png)

-- The balanced accuracy score is 65%.
-- The high_risk precision is about 1% only with 66% sensitivity which makes a F1 of 2%
-- Due to the high number of the low_risk population, its precision is 99% with a sensitivity of 64%.

### Undersampling

![Undersampling](https://user-images.githubusercontent.com/102183530/182263684-01425ba2-42a9-484b-bd9b-fd263b1d7f4d.png)

-- The balanced accuracy score is 53%.
-- The high_risk precision is about 1% only with 61% sensitivity which makes a F1 of 1%
-- Due to the high number of the low_risk population, its precision is 99% with a sensitivity of 45%.

### Combination (Over & Under) Sampling

![ComboSampling](https://user-images.githubusercontent.com/102183530/182263699-6084ee22-c0e5-4eb5-9b22-72b1f1a40875.png)

-- The balanced accuracy score is 64%.
-- The high_risk precision is about 1% only with 70% sensitivity which makes a F1 of 2%
-- Due to the high number of the low_risk population, its precision is 99% with a sensitivity of 57%.

### Balanced Random Forest Classifier

![BalRanForest](https://user-images.githubusercontent.com/102183530/182265131-38998545-6f43-4c94-a64d-ff27c538424e.png)

-- The balanced accuracy score is 79%.
-- The high_risk precision is 3% with 70% sensitivity which makes a F1 of 6%
-- Due to the high number of the low_risk population, its precision is 99% with a sensitivity of 87%.

### Easy Ensemble Classifier

![EasyEnsemble](https://user-images.githubusercontent.com/102183530/182265170-11c139a6-6298-4abe-b59a-f0ed9c86aa2d.png)

-- The balanced accuracy score is 93%.
-- The high_risk precision is 9% only, with 92% sensitivity which makes a F1 of 16%
-- Due to the high number of the low_risk population, its precision is 99% with a sensitivity of 94%.

### Features with Scores
  #### (sorted from most important to least)
  
![Screen Shot 2022-08-01 at 8 05 02 PM](https://user-images.githubusercontent.com/102183530/182265369-cac94f2c-feb1-4bed-9980-cef0fd1d325a.png)

The most "important" feature when considering a high vs low credit risk at 7.9% is 'Total Recent Principle[Amount?]' , with four ('Total Payment', 'Total Payment Inv', 'Total Received Intrest', and 'Last Payment Amount') all at around 5.9% to 5% range.

## Summary: 
Based on these results, the smallest balanced accuracy of 53% (so just over half) from Undersampling, to the highest at 93% from the Easy Ensemble Classifier; so it detects nearly all the high risk credit.  However, with such low precision, the bank would lose a lot of business due to falsly detecting high-credit risks.  This is an example of where for business purposes, the bank would want to capture all the low-risks loans instead, and build in a 'write-off' contingency for those few high-risk that do slip through.   

All the models used to perform the credit risk analysis show weak precision in determining if a credit risk is high.
Both of the 'Ensemble' models brought improvement; specfically to the sensitivity of the high risk credits.  Their F1 scores, however topped out at 6% and 16%, the highest in the entire set of models.

The population of which is so low compared to the 51,000 total samples, that WAY more data would be needed to train and run any of these actual models.

I cannot for these reasons recommend ANY of these models.  The bank should go back to the data board, and see if either they can find more factors that would create low-risk situations, buy-here-pay-here, or consider other factors to mitigate some of the risk factors, like also condisering cell-phone or utility payment data to review.
