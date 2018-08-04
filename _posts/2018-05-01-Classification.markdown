---
layout: post
title:  "Classification"
date:   2018-05-01  18:43:31 +0800
categories: jekyll update
---

supervised learning

# Classification

- statistics learning theory

## loss functions
measure classification error

![lossfunction](../pictures/lossfunction.png)

![lossfunctionmodel](../pictures/lossfunctionmodel.png)


## Statistics learning theory
- regulation
- Ockham’s Razor: The best models are simple models that fit the data well


## Logistic regression
- logistic regression formula
![Logistic_regression](../pictures/Logistic_regression.png)
- minimize loss functions


- [sklearn.linear_model.LogisticRegression](http://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html)

## Maximum likelihood perspective



- evaluation method for classifier
confusion matrix
classification error
(FN+FN)/N


## ROC curves(receiver operating characteristic curve)

[wikiROC](https://zh.wikipedia.org/wiki/ROC%E6%9B%B2%E7%BA%BF?spm=5176.11409106.555.1.531e6b270Im2Yx#.E6.9B.B2.E7.B7.9A.E4.B8.8B.E9.9D.A2.E7.A9.8D.EF.BC.88AUC.EF.BC.89)



















- ROC curves algorithm
- Creating a Classifier with Python

# Decision Tree
- machine learning classifier

- the collection of `if then` regulation
- Each leaf node of the decision tree represents a classification


entropy:

![Entropy](../pictures/Entropy.png)

gini index:


Information Gain:

![information_gain](../pictures/information_gain.png)

pick largest information_gain


Parameters:
- max_deepth
- min_samples_leaf


how to deal with NAN values?


[Decision Tree](http://www.saedsayad.com/decision_tree.htm)

### RandomForest

random select feature and sample

## GBDT（Gradient Boost Decision Tree）


- [Greedy Function Approximation: A Gradient Boosting Machine](https://statweb.stanford.edu/~jhf/ftp/trebst.pdf)



- [A Kaggle Master Explains Gradient Boosting](http://blog.kaggle.com/2017/01/23/a-kaggle-master-explains-gradient-boosting/)



### XGBoost（eXtreme Gradient Boosting）
```
import xgboost as xgb
# read in data
dtrain = xgb.DMatrix('demo/data/agaricus.txt.train')
dtest = xgb.DMatrix('demo/data/agaricus.txt.test')

# specify parameters via map
param = {'max_depth':2, 'eta':1, 'silent':1, 'objective':'binary:logistic' }
num_round = 2
bst = xgb.train(param, dtrain, num_round)

# make prediction
preds = bst.predict(dtest)
```



- [XGBoost slides](https://homes.cs.washington.edu/~tqchen/pdf/BoostedTree.pdf)

- [XGBoost Documents](https://xgboost.readthedocs.io/en/latest/model.html)

- [GBDT and XGBoost](https://blog.csdn.net/Liangjun_Feng/article/details/80142724?spm=5176.9876270.0.0.35fde44aVHoKRf)
- [XGBoost_API](https://xgboost.readthedocs.io/en/latest/python/python_api.html)


#### XGBoost API
- xgboost.train()
- xgboost.cv()
- xgboost.XGBClassifier()

- xgboost.Booster()

 - get_fscore(fmap='')
 Get feature importance of each feature.




### Light GBM

Light GBM is a gradient boosting framework that uses tree based learning algorithm

[document](https://lightgbm.readthedocs.io/en/latest/Parameters.html)

[chinese-document](http://lightgbm.apachecn.org/cn/latest/Python-Intro.html)


problems:
1.module lightgbm have no method dataset???
















# Improving Machine Learning Models



# Ensemble learning(multi_classifier-system)
- it combine with a series individual learner using some strategy.
- individual learner need precision and diversity.

## Boosting



## Bagging










# Another Reading
- [gitbook](https://legacy.gitbook.com/book/yoyoyohamapi/mit-ml/details)

- [scikit-learn-chinese](http://sklearn.apachecn.org/cn/0.19.0/)

- [scikit-learn](http://scikit-learn.org/stable/index.html)

- [interview questions](https://blog.csdn.net/sinat_35512245/article/details/78796328)

- [learn-machine-learning](https://www.kaggle.com/dansbecker/learn-machine-learning/notebook)


# problems
1. full singular value decomposition??
