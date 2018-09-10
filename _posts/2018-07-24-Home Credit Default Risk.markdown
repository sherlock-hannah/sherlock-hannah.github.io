---
layout: post
title:  "Home Credit Default Risk"
date:   2018-07-24 18:43:31 +0800
categories: jekyll update
---


## Description
Many people struggle to get loans due to insufficient or non-existent credit histories. And, unfortunately, this population is often taken advantage of by untrustworthy lenders.

Home Credit strives to broaden financial inclusion for the unbanked population by providing a positive and safe borrowing experience.

## Goal
Home Credit makes use of a variety of alternative data--including telco and transactional information--to predict their clients' repayment abilities.

## Metric: ROC AUC
- `sklearn.metrics.roc_auc_score(y_true, y_score, average=’macro’, sample_weight=None)`
 [sklearn.metrics.roc_auc_score](http://scikit-learn.org/stable/modules/generated/sklearn.metrics.roc_auc_score.html#sklearn.metrics.roc_auc_score)

## Raw Data
1.application table


| variable     | description         |   
| :------------| :-------------    |
| SK_ID_CURR      | application id |
| NAME_CONTRACT_TYPE | Identification if loan is cash or revolving|
| FLAG_OWN_REALTY|Flag if client owns a house or flat |
| CNT_CHILDREN | Number of children the client has      |
| AMT_INCOME_TOTAL | Income of the client                    |
| AMT_CREDIT         | Credit amount of the loan                  |
| AMT_ANNUITY| Loan annuity|
| AMT_GOODS_PRICE      |For consumer loans it is the price of the goods for which the loan is given|
| NAME_TYPE_SUITE |Who was accompanying client when he was applying for the loan|
| NAME_INCOME_TYPE|Clients income type (businessman, working, maternity leave|
| NAME_EDUCATION_TYPE | Level of highest education the client achieved |
| DAYS_EMPLOYED |How many days before the application the person started current employment|


![userdistribution](/pictures/home_credit_table.png)


## Data analysis
### Distribution of the Target Column


### Examine Missing Values¶






1. add diff feature
2. add period feature







## Reference
- [Open Solution JournalLB 0.804](https://www.kaggle.com/c/home-credit-default-risk/discussion/57175)
- [LightGBM with smarter features](https://github.com/neptune-ml/open-solution-home-credit/wiki/LightGBM-with-smarter-features)

## Problem
1. how to join different table by primary key
