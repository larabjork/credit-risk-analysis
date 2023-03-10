# Credit Risk Analysis
Data Bootcamp week 18 - supervised machine learning

## Overview
The purpose of this independent challenge exercise was to build and evaluate multiple supervised machine learning models. These models were used to evaluate credit risk, starting with more than 115,000 rows and 86 columns of information on past credit usage by consumers. The source data is saved [here](https://github.com/larabjork/credit-risk-analysis/blob/main/LoanStats_2019Q1.csv).

We were provided with a Jupyter notebook that included code to load and partially preprocess data. The assignment involved: 

* Converting all string data to numeric values,
* Separating "loan status" (the target) out from the rest of the data (the input features),
* Splitting the data into training and testing buckets,
* Resampling data with six different models (two of which were ensemble learners) before training each model,
* Making predictions with each model using the test data, and
* Calculating balanced accuracy scores, confusion matrixes, and imbalanced classification reports for each model.

## Results

### Balanced Accuracy Scores
For all six models, a balanced accuracy score was calculated with Sci-kit Learn. The rounded results, in descending order, are as follows (Unrounded results and unsorted results are shown in screenshots from Jupyter Lab).

| Model | Balanced Accuracy Score |
| ----- | ----------------------- |
| Easy Ensembler AdaBoost Classifier | 0.93 |
| Balanced Random Forest Classifier | 0.79 |
| Naive Random Oversampling | 0.66 |
| SMOTE Oversampling | 0.64 |
| SMOTEENN Combination Sampling | 0.64 |
| Cluster Centroid Undersampling | 0.53 |

![screenshot of resampling accuracy score results](https://github.com/larabjork/credit-risk-analysis/blob/main/images/resampling_accuracy_score_summary.png)

![screenshot of ensemble accuracy score results](https://github.com/larabjork/credit-risk-analysis/blob/main/images/ensemble_accuarcy_score_summary.png)

### Precision and Recall Scores
For all six models, an imbalanced classification report was generated with Imbalanced Learn. The unrounded, sorted results for precision and recall, in descending order, are as follows (Unsorted, unrounded results are shown in screenshots from Jupyter Lab).

#### Precision Scores
A precision score is calculated from all positive predictions (i.e., both true positives and false positives). It tells us how many of those predictions are actually positive. 

| Model | Precision: High-Risk | Precision: Low-Risk | Average / Total |
| ----- | -------------------- | ------------------- | --------------- |
| Easy Ensembler AdaBoost Classifier | 0.08 | 1.00 | 0.99 |
| Balanced Random Forest Classifier | 0.03 | 1.00 | 0.99 |
| Naive Random Oversampling | 0.01 | 1.00 | 0.99 |
| SMOTE Oversampling | 0.01 | 1.00 | 0.99 |
| SMOTEENN Combination Sampling | 0.01 | 1.00 | 0.99 |
| Cluster Centroid Undersampling | 0.01 | 1.00 | 0.99 |

#### Recall Scores
Recall is calculated from all actually positive instances (i.e., both true positives and false negatives). It tells us how many actually positive cases were predicted correctly (as positives).

| Model | Recall: High-Risk | Recall: Low-Risk | Average / Total |
| ----- | ----------------- | ---------------- | --------------- |
| Easy Ensembler AdaBoost Classifier | 0.91 | 0.94 | 0.94 |
| Balanced Random Forest Classifier | 0.68 | 0.89 | 0.89 |
| SMOTE Oversampling | 0.63 | 0.65 | 0.65 |
| Naive Random Oversampling | 0.70 | 0.62 | 0.62 |
| SMOTEENN Combination Sampling | 0.70 | 0.58 | 0.58 |
| Cluster Centroid Undersampling | 0.67 | 0.39 | 0.39 |

![screenshot of resampling classification reports ](https://github.com/larabjork/credit-risk-analysis/blob/main/images/resampling_classification_report_summary.png)

![screenshot of ensemble classification reports](https://github.com/larabjork/credit-risk-analysis/blob/main/images/ensemble_classification_report_summary.png)

## Summary 

### Overall Performance of the Models
In general, the two ensemble models performed better than the resampling models. Overall, the Easy Ensemble AdaBoost Classifier performed better than all the other models in terms of accuracy, precision, and recall. Also, all models were more sensitive than precise (had better recall scores than precision scores); this imbalance is reflected in their F1 scores (the closer a score is to 1, the better).

Since a primary goal of our models is to help identify high-risk instances, understanding each model's ability to reliably identify high-risk applicants is important. When looking only at the high-risk predictions, none of the models do a very good job. Even the Easy Ensemble AdaBoost Classifier only achieves an F1 score of 0.14 for actually high-risk instances.

### Recommendations
Among the models already used, the Easy Ensemble AdaBoost Classifier is the best choice, although this is not an enthusiastic recommendation, due to the weak performance of this model in predicting high-risk cases. Further work should include:

* re-running both ensemble models, eliminating the features listed below, which were ranked at 0 importance of by the Balanced Random Forest Classifier.
![screenshot of features ranked at 0 importance](https://github.com/larabjork/credit-risk-analysis/blob/main/images/low_rank_feature_importances.png)

* investigating other models, with an emphasis on ensemble models, since this type of model performed better than the resampling models.