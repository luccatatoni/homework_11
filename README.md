# Unit 11 - Risky Business
## Background
Mortgages, student and auto loans, and debt consolidation are just a few examples of credit and loans that people seek online. Peer-to-peer lending services such as Loans Canada and Mogo let investors loan people money without using a bank. However, because investors always want to mitigate risk, a client has asked that you help them predict credit risk with machine learning techniques.

In this assignment it was asked tobuild and evaluate several machine learning models to predict credit risk using data you'd typically see from peer-to-peer lending services. Credit risk is an inherently imbalanced classification problem (the number of good loans is much larger than the number of at-risk loans), so it was needed to employ different techniques for training and evaluating models with imbalanced classes. It was used the imbalanced-learn and Scikit-learn libraries to build and evaluate models using the two following techniques:

1. Resampling
2. Ensemble Learning

- - -
#### Resampling
It was used the imbalanced learn library to resample the LendingClub data and build and evaluate logistic regression classifiers using the resampled data.

It was tested:

1. Oversample the data using the `Naive Random Oversampler` and `SMOTE` algorithms.
2. Undersample the data using the `Cluster Centroids` algorithm.
3. Over- and undersample using a combination `SMOTEENN` algorithm.


* Which model had the best balanced accuracy score?
> SMOTE Oversample, with an accuracy score of 0.9948. It is worth noting that other models had a very high accuracy score
> Random Oversampling: 0.9947
> Undersampling: 0.9828
> Combination (SMOTEENN): 0.9947
> Simple Logistic Regression: 0.9543

* Which model had the best recall score?
> 3 models had the best recall score (1.00 for high_risk and 0.99 for low_risk): Naive Random Oversampling / SMOTE oversampling and combination (over and undersampling)

* Which model had the best F1 score?
> 3 models had the best recall score 0.92 for high_risk and 1.00 for low_risk). The Models are: Naive Random Oversampling / SMOTE / Combination (over and under sampling)

#### Ensemble Learning
In this section, it was about to train and compare two different ensemble classifiers to predict loan risk and evaluate each model. It was used the Random Fores Classifier, Balanced Random Forest Classifier and Easy Ensemble Classifier.

It was made:
1. Train the model using the quarterly data from LendingClub provided in the `Resource` folder.

2. Calculate the balanced accuracy score from `sklearn.metrics`.

3. Display the confusion matrix from `sklearn.metrics`.

4. Generate a classification report using the `imbalanced_classification_report` from imbalanced learn.

5. For the balanced random forest classifier only, print the feature importance sorted in descending order (most important feature to least important) along with the feature score.

Assessment:

* Which model had the best balanced accuracy score?
The Random Forest Classifier had the best accuracy score (lowest amount of false negatives and false positives)

* Which model had the best recall score?
1. Random Forest with 0.32 / 1.0 (average 1.0)
2. Easy Ensemble Classifier with 0.92 / 0.94 (average 0.94 )
3. Balanced Random Forest with 0.64 / 0.92 (average 0.92)

* Which model had the best geometric mean score?
1. Easy Emsemble Classifier: 0.93 / 0.93 (average 0.93)
2. Balanced Random Forest with 0.77 / 0.77 (average 0.77)
3. Random Forest with 0.56 / 0.56 (average 0.56)

* What are the top three features?
For Balanced Random Forest Classifier (for Easy Emsemble Classifier it was not possible to list the features):
(0.07239290541174957, 'total_rec_prncp'),
(0.06733303127962115, 'last_pymnt_amnt'),
(0.06718324331180901, 'total_pymnt_inv'),
(0.05746049006493996, 'total_pymnt'),
(0.05259921495573907, 'total_rec_int'),
(0.029610942008818013, 'int_rate'),
(0.02204428929077674, 'issue_d_Jan-2019'),
(0.016566562106507986, 'dti'),
(0.01635120518538894, 'mo_sin_old_rev_tl_op'),
(0.01594212905787986, 'out_prncp')]

