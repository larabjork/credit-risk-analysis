# Credit Risk Analysis
Data Bootcamp week 18 - supervised machine learning

## Overview
Purpose of analysis

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
For all six models, an imbalanced classification report was generated with Imbalanced Learn. The unrounded, sorted results for precision and recall, in descending order, are as follows (Unsorted results are shown in screenshots from Jupyter Lab).

#### Precision Scores

| Model | Precision: High-Risk | Precision: Low-Risk | Average / Total |
| ----- | -------------------- | ------------------- | --------------- |
| Easy Ensembler AdaBoost Classifier | 0.08 | 1.00 | 0.99 |
| Balanced Random Forest Classifier | 0.03 | 1.00 | 0.99 |
| Naive Random Oversampling | 0.01 | 1.00 | 0.99 |
| SMOTE Oversampling | 0.01 | 1.00 | 0.99 |
| SMOTEENN Combination Sampling | 0.01 | 1.00 | 0.99 |
| Cluster Centroid Undersampling | 0.01 | 1.00 | 0.99 |

#### Recall Scores
| Model | Recall: High-Risk | Recall: Low-Risk | Average / Total |
| ----- | ----------------- | ---------------- | --------------- |
| Easy Ensembler AdaBoost Classifier | 0.91 | 0.94 | 0.94 |
| Balanced Random Forest Classifier | 0.68 | 0.89 | 0.89 |
| Naive Random Oversampling | 0.70 | 0.62 | 0.62 |
| SMOTE Oversampling | 0.63 | 0.65 | 0.65 |
| SMOTEENN Combination Sampling | 0.70 | 0.58 | 0.58 |
| Cluster Centroid Undersampling | 0.67 | 0.39 | 0.39 |


## Summary 
Sum up results
Recommendation on which model to use, or no rec but justification for that