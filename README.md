# LendingClub Credit Risk Analysis Overview

In this analysis, the focus is on Supervised Learning using a free dataset from LendingClub, a P2P lending service company to evaluate and predict credit risk. The reason why this is called "Supervised Learning" is because the data includes a labeled outcome.

To complete this analysis, different Machine Learning techniques are used to train and evaluate the data with unbalanced classes. The dataset from the LendingClub has an unbalanced classification problem due to the number of good loans significantly outweighing the amount of risky loans. In order balance out the classifications to allow for more meaningful predictions and improve the accuracy score, various Machine Learning algorithms are employed to resample the data. These algorithms include RandomOverSampler, SMOTE, ClusterCentroids, SMOTEENN, BalancedRandomForestClassifier, and EasyEnsembleClassifier.  A recomendation of which model to use is provided based on the analysis results.

# Results
![Alt Text](https://github.com/syoder821/Credit_Risk_Analysis/blob/main/Resources/Images/Training_Testing.png)
## Deliverable 1: Use Resampling Models to Predict Credit Risk
### Oversampling
- RandomOverSampler Model
 
Counter({'low_risk': 51366, 'high_risk': 51366})  
The model classified 51366 records each as High risk and Low risk.

![Alt Text](https://github.com/syoder821/Credit_Risk_Analysis/blob/main/Resources/Images/Random_oversampling.png) 
- SMOTE Model
![Alt Text](https://github.com/syoder821/Credit_Risk_Analysis/blob/main/Resources/Images/Smote.png)
### Undersampling
- ClusterCentroids Model

Counter({'high_risk': 246, 'low_risk': 246})  
The model classified 246 records each as High risk and Low risk.
![Alt Text](https://github.com/syoder821/Credit_Risk_Analysis/blob/main/Resources/Images/Clustered_centroids.png)

## Deliverable 2: Use the SMOTEENN algorithm to Predict Credit Risk
### Combinational Sampling
SMOTEENN Model combines aspects from both oversampling and undersampling resulting in 68458 recordes classified as High risk and 62022 records classified as Low risk.   
Counter({'high_risk': 68458, 'low_risk': 62022})
![Alt Text](https://github.com/syoder821/Credit_Risk_Analysis/blob/main/Resources/Images/Smoteen.png)

## Deliverable 3: Use Ensemble Classifiers to Predict Credit Risk
### Ensemble Classifiers
BalancedRandomForestClassifier
![Alt Text](https://github.com/syoder821/Credit_Risk_Analysis/blob/main/Resources/Images/BalancedRandomForestClassifier.png)

EasyEnsembleClassifier
![Alt Text](https://github.com/syoder821/Credit_Risk_Analysis/blob/main/Resources/Images/EasyEnsembleClassifier.png)

# Summary
All the models show weak precision in determining if a credit risk is high.
The Ensemble models brought improvment especially on the sensitivity of the high risk credits.
The EasyEnsembleClassifier model shows a recall of 92% so it detects almost all high risk credit. On the other hand, with a low precision, a lot of low risk credits are still falsely detected as high risk which would penalize the bank's credit strategy and have a negative impact on its revenue by missing those business opportunities.
If the bank's strategy is to prioritize detecting high credit risk and is willinig to accept losing revenue due to the high number of falsely detected "low risk" canditates flagged as high risk then I would recommend the EasyEnsembleClassifier Model.  If the priority is to maximize business opportunities with risk of a small percentage of canditates defaulting then I wouldn't recommend using any of the models.    

### Models ranked in descending order based on "High Risk" results:
- EasyEnsembleClassifier: 93.2% accuracy, 9% precision, 92% recall, and 16% F1 Score 
- BalancedRandomForestClassifier:78.9% accuracy, 3% precision, 70% recall, and 6% F1 Score 
- SMOTE: 66.2% accuracy, 1% precision, 63% recall, and 2% F1 Score
- SMOTEENN: 68.8% accuracy, 1% precision, 80% recall, and 2% F1 Score
- RandomOverSample: 65.7% accuracy, 1% precision, 71% recall, and 2% F1 Score
- ClusterCentroids: 54.4% accuracy, 1% precision, 69% recall, and 1% F1 Score

# Resources
- Dataset: LoansStats_2019Q1
- Software: Python 3.7.11, Jupyter Notebook 6.4.6
