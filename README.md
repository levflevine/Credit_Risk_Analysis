# Credit_Risk_Analysis

## Overview of the Analysis

### Purpose

Evaluate six machine learning models with unbalanced classes by using resampling to determine which is better at predicting credit risk and make a written recommendation on whether they should be used to predict credit risk.  

### Approach

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, a data oversampling is performed using the *RandomOverSampler* and *SMOTE* algorithms, and an undersampling is applied to the data using the *ClusterCentroids* algorithm. Then, a combinatorial approach of over- and undersampling using the *SMOTEENN* algorithm is applied. Next, two additional machine learning models that reduce bias, *BalancedRandomForestClassifier* and *EasyEnsembleClassifier* are applied and compared to predict credit risk.  

### Deliverables: 

1. Use Resampling Models to Predict Credit Risk
2. Use the SMOTEENN Algorithm to Predict Credit Risk
3. Use Ensemble Classifiers to Predict Credit Risk
4. A Written Report on the Credit Risk Analysis 

### Tools and Data Sources

#### Tools

- Python Scripts
- Pandas Library
- Sklearn Library
- Imblearn Library


#### Data Sources

- [Credit card credit dataset from LendingClub](https://2u-data-curriculum-team.s3.amazonaws.com/dataviz-online/module_17/Module-17-Challenge-Resources.zip)

## Results

### Results Summary

#### Balanced Accuracy Score 

- RandomOverSampler:                0.65
- SMOTE:                            0.66
- ClusterCentroids:                 0.54
- SMOTEENN:                         0.67
- BalancedRandomForestClassifier:   0.79
- EasyEnsembleClassifier:           0.93

#### Precision Scores for High Risk Loans

- RandomOverSampler:                0.01
- SMOTE:                            0.01
- ClusterCentroids:                 0.01
- SMOTEENN:                         0.01
- BalancedRandomForestClassifier:   0.03
- EasyEnsembleClassifier:           0.09

#### Precision Scores for Low Risk Loans

- RandomOverSampler:                1.00
- SMOTE:                            1.00
- ClusterCentroids:                 1.00
- SMOTEENN:                         1.00
- BalancedRandomForestClassifier:   1.00
- EasyEnsembleClassifier:           1.00

#### Recall Scores for High Risk Loans

- RandomOverSampler:                0.71
- SMOTE:                            0.63
- ClusterCentroids:                 0.69
- SMOTEENN:                         0.73
- BalancedRandomForestClassifier:   0.70
- EasyEnsembleClassifier:           0.92

#### Recall Scores for Low Risk Loans

- RandomOverSampler:                0.58
- SMOTE:                            0.68
- ClusterCentroids:                 0.40
- SMOTEENN:                         0.60
- BalancedRandomForestClassifier:   0.87
- EasyEnsembleClassifier:           0.94

![Results](/Resources/vine_reviews_5_star.png)

## Summary

### Is there any positivity bias for reviews in the Vine program

Summary Statistics for the non-Vine reviews with a 5-Star Rating

![Free_Summary Stats](/Resources/free_summary_stats.png)

Summary Statistics for the Vine-participating reviews with a 5-Star Rating

![Paid_Summary_Stats](/Resources/paid_summary_stats.png)

**Initial Conclusion**. There is some level of positivity bias for the reviews in the Vine Program:  the mean of the ratings from the people participating in the Vine Program is 4.09/5.00 versus the mean of the ratings from the people, who dont' participate in the Vine program: 3.65/5.00. People in the Vine program, who are getting paid for providign the reviews, tend to provide better ratings. This initial conclusion needs to be statistically validated.

### One additional analysis with the dataset to support the conclusion

To validate the conclusion above, we need to perform a two-sample T-Test that will help to determine if the ratings for people in and out of the Vine program are statistically different. 

![T-Test Summary](/Resources/2-sample-t-test.png)

**Conclusion**: Based on the **0.05 significance level**, there is **no statistical difference** of the review ratings mean for the people in the Vine program and the review ratings mean for the people not enrolled the Vine program: 

- **the p-value = 1.78e-20, which is below our significance level**.

**Hence, we cannot reject the Null Hypothesis and the final conclusion is that there is no statistically significant positivity bias for the reviews in the Vine Program. People, both in and out of the Vine program, tend to provide statistically comparable reviews regardless or whether or not they are being paid.**

