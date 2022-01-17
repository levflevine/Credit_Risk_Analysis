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

### Key Metrics

#### Balanced Accuracy Score 

- RandomOverSampler: 0.65
- SMOTE: 0.66
- ClusterCentroids: 0.54
- SMOTEENN: 0.67
- BalancedRandomForestClassifier:  0.79
- EasyEnsembleClassifier: 0.93

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

### Result Details

#### RandomOverSampler

Balanced Accuracy Score:

![BalancedAccuracyScore](/Resources/Random_Over_Sampler_Balanced_Accuracy_Score.png)

Confusion Matrix:

![ConfusionMatrix](/Resources/Random_Over_Sampler_Confusion_Matrix.png)

Classification Report:

![ClassificationReport](/Resources/Random_Over_Sampler_Classification_Report.png)

#### SMOTE

![BalancedAccuracyScore](/Resources/SMOTE_Balanced_Accuracy_Score.png)

Confusion Matrix:

![ConfusionMatrix](/Resources/SMOTE_Confusion_Matrix.png)

Classification Report:

![ClassificationReport](/Resources/SMOTE_Classification_Report.png)

#### ClusterCentroids

![BalancedAccuracyScore](/Resources/Cluster_Centroids_Balanced_Accuracy_Score.png)

Confusion Matrix:

![ConfusionMatrix](/Resources/Cluster_Centroids_Confusion_Matrix.png)

Classification Report:

![ClassificationReport](/Resources/Cluster_Centroids_Classification_Report.png)

#### SMOTEENN

![BalancedAccuracyScore](/Resources/SMOTEENN_Balanced_Accuracy_Score.png)

Confusion Matrix:

![ConfusionMatrix](/Resources/SMOTEENN_Confusion_Matrix.png)

Classification Report:

![ClassificationReport](/Resources/SMOTEENN_Classification_Report.png)

#### BalancedRandomForestClassifier

![BalancedAccuracyScore](/Resources/Ensemble_Balanced_Accuracy_Score.png)

Confusion Matrix:

![ConfusionMatrix](/Resources/Ensemble_Confusion_Matrix.png)

Classification Report:

![ClassificationReport](/Resources/Ensemble_Classification_Report.png)

#### EasyEnsembleClassifier

![BalancedAccuracyScore](/Resources/Easy_Ensemble_Balanced_Accuracy_Score.png)

Confusion Matrix:

![ConfusionMatrix](/Resources/Easy_Ensemble_Confusion_Matrix.png)

Classification Report:

![ClassificationReport](/Resources/Easy_Ensemble_Classification_Report.png)

## Summary

Below are the conclusions by each ML model:

### RandomOverSampler    

From the confusion matrix results, the **Precision** for the high-risk loan applications is **extremely low (1)**, indicating a large number of false positives, which indicates an unreliable positive classification. While the other metrics seems OK, including the reasonable **F1 score of 73** and **Balanced Accuracy Score of 65**, **the model is not recommended to be practically used** in predicting the credit risk and approving/rejecting the loans. If the bank used the model, it would reject too many low-risk applications (99% of the rejected applications should have been approved) and loose too much business,manmy low-risk customers, which will impact customer acquisition/retention and market share.

### SMOTE        

The SMOTE model shows sligh improvements in comparison to the RandomOverSampler model. However, it suffers same defficiencies that make it impractical for the real-life bank application. 

From the confusion matrix results, the **Precision** for the high-risk loan applications is **extremely low (1)**, indicating a large number of false positives, which indicates an unreliable positive classification. While the other metrics seems OK, including the reasonable **F1 score of 81** and **Balanced Accuracy Score of 66**, **the model is not recommended to be practically used** in predicting the credit risk and approving/rejecting the loans. If the bank used the model, it would reject too many low-risk applications (99% of the rejected applications should have been approved) and loose too much business,manmy low-risk customers, which will impact customer acquisition/retention and market share.

### ClusterCentroids 

The ClusterCentroids undersampling model demonstarted inferior results in comparion to the two previous oversampling models (RandomOverSampler and SMOTE). 

From the confusion matrix results, the **Precision** for the high-risk loan applications is **extremely low (1)**, indicating a large number of false positives, which indicates an unreliable positive classification. The other metrics seems rather low, including the **F1 score of 56** and **Balanced Accuracy Score of 54**, and as a result, **the model is not recommended to be practically used** in predicting the credit risk and approving/rejecting the loans. If the bank used the model, it would reject too many low-risk applications (99% of the rejected applications should have been approved) and loose too much business,manmy low-risk customers, which will impact customer acquisition/retention and market share.

### SMOTEENN      

The SMOTEENN cobination sampling model demonstarted inferior results in comparion to the two oversampling models (RandomOverSampler and SMOTE), but better results than the undersampling model (ClusterCentroids). 

From the confusion matrix results, the **Precision** for the high-risk loan applications is **extremely low (1)**, indicating a large number of false positives, which indicates an unreliable positive classification. While the other metrics seems OK, including the reasonable **F1 score of 75** and **Balanced Accuracy Score of 67**, **the model is not recommended to be practically used** in predicting the credit risk and approving/rejecting the loans. If the bank used the model, it would reject too many low-risk applications (99% of the rejected applications should have been approved) and loose too much business,manmy low-risk customers, which will impact customer acquisition/retention and market share.

### BalancedRandomForestClassifier

The BalancedRandomForestClassifier ensemble learning model demonstarted significantly higher results in comparion to all the previous models. However, it still suffers from extremely low precision and is not recommended.

From the confusion matrix results, the **Precision** for the high-risk loan applications is **extremely low (3)**, indicating a large number of false positives, which indicates an unreliable positive classification. While the other metrics seems solid, including the high **F1 score of 93** and **Balanced Accuracy Score of 79**, **the model is not recommended to be practically used** in predicting the credit risk and approving/rejecting the loans. If the bank used the model, it would reject too many low-risk applications (97% of the rejected applications should have been approved) and loose too much business,manmy low-risk customers, which will impact customer acquisition/retention and market share.

### EasyEnsembleClassifier        

The EasyEnsembleClassifier demonstrated best results out the models explored in this project. It still has significant defficiencies, but after additional cost-benefit analysis and validation and/or in combination with additional risk assurance processes, it could potentially be used by the bank.

From the confusion matrix results, the **Precision** for the high-risk loan applications is **low (9)**, indicating a large number of false positives, which indicates an unreliable positive classification. The other metrics is solid, including a very high **F1 score of 97** and **Balanced Accuracy Score of 93**. 

### Final Recommendation

**The EasyEnsembleClassifier model can be recommended for the use with the following reservations.** 

A further validation of the feasibility of using the EasyEnsembleClassifier model is needed. The validation can include conducting the following cost-benefit analysis:

1. Evaluate the **average revenue per user (ARPU)** and **profit margin per user** - how much revenue and profit each credit card customer generates to the bank on average
2. Multiply the average profit margin per user by the number of erroneously rejected low-risk customers
3. *This will generate the loss that the bank will incure if it were to implement and blindly follow the recommendations of the model*
4. Evaluate the average loss per high-risk customer
5. Multiply by the number of true high-risk customers
6. *This will generate the loss that the bank will incure if it accepted all the applications and did not perform any risk analysis*
7. **Compare Line # 3 and Line # 6. If the loss in # 6 is lower than the loss in # 3, the bank should not use the model.**
8. **If the opposite is true, the model will generate incremental benefits to the bank and can be used.** 

If the model is used, it could be applied in combination with additional processes that will reduce the level of false-positive high risk classifications. This can be accomplished, for instance, by sending requests for additional evidence to the applicants classified as high-risk, before rejecting their application. The process to collect additional evidence can signifciantly improve the precision of high-risk classification.

In addition, the bank could reengineer the model features and take out the least important ones that create noise to the model to improve the model performance.



