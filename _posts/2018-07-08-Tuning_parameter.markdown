---
layout: post
title:  "Tuning parameter "
date:   2018-07-04 18:43:31 +0800
categories: jekyll update
---
[Complete Guide to Parameter Tuning in XGBoost (with codes in Python)](https://www.analyticsvidhya.com/blog/2016/03/complete-guide-parameter-tuning-XGBoost-with-codes-python/)


## sklearn.model_selection.GridSearchCV

```
from sklearn.model_selection import GridSearchCV
parameters = {'max_depth':[3,6,10,15], 'min_samples_leaf':[3,6,10,15],'min_samples_split':[5,10,20,50]}
model = DecisionTreeClassifier(random_state=42)

clf = GridSearchCV(model, parameters,cv=3)
clf.fit(X_train, y_train)

## Make predictions
y_train_pred = clf.predict(X_train)
y_test_pred = clf.predict(X_test)
## Calculate the accuracy
train_accuracy = accuracy_score(y_train, y_train_pred)
test_accuracy = accuracy_score(y_test, y_test_pred)

print('The training accuracy is', train_accuracy)
print('The test accuracy is', test_accuracy)
print('best params',clf.best_params_)
```


[sklearn.model_selection.GridSearchCV](http://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html)
- cv : Determines the cross-validation splitting strategy.
- scoring :[The scoring parameter: defining model evaluation rules](http://scikit-learn.org/stable/modules/model_evaluation.html#scoring-parameter)

## sklearn.base.BaseEstimator

- get_params(deep=True)
:Get parameters for this estimator.
- set_params(params)
:Set the parameters of this estimator.












## Parameter Tuning in XGBoost

- [Complete Guide to Parameter Tuning in Gradient Boosting (GBM) in Python](https://www.analyticsvidhya.com/blog/2016/02/complete-guide-parameter-tuning-gradient-boosting-gbm-python/)
- [Complete Guide to Parameter Tuning in Gradient Boosting (GBM) in Python in chinese](https://blog.csdn.net/han_xiaoyang/article/details/52663170)
- [XGBoost](https://xgboost.readthedocs.io/en/latest/how_to/param_tuning.html)
- [Complete Guide to Parameter Tuning in XGBoost (with codes in Python)](https://www.analyticsvidhya.com/blog/2016/03/complete-guide-parameter-tuning-xgboost-with-codes-python/)
- [Complete Guide to Parameter Tuning in XGBoost (with codes in Python) in chinese](https://blog.csdn.net/han_xiaoyang/article/details/52665396)

- [XGBoost Parameters](https://xgboost.readthedocs.io/en/latest/parameter.html)

- [meaning of XGBoost Parameters in chinese](https://blog.csdn.net/wzmsltw/article/details/50994481)

### booster

The first way is to directly control model complexity

#### max_depth
- The maximum depth of a tree, same as GBM.
- control over-fitting

#### min_child_weight:
- Defines the minimum sum of weights of all observations required in a child
- Too high values can lead to under-fitting

#### gamma(default 0)
- Gamma specifies the minimum loss reduction required to make a split.

add randomness to make training robust to noise

#### subsample
- Denotes the fraction of observations to be randomly samples for each tree.
- Lower values prevents overfitting but too small values lead to under-fitting.
- Typical values: 0.5-1

#### colsample_bytree
- Similar to max_features in GBM. Denotes the fraction of columns to be randomly samples for each tree
- Typical values: 0.5-1

#### eta
- Analogous to learning rate in GBM
- Makes the model more robust by shrinking the weights on each step
- Typical final values to be used: 0.01-0.2
- You can also reduce stepsize eta, but needs to remember to increase num_round when you do so

#### n_estimators
- n_estimators specifies how many times to go through the modeling cycle described above.





### Learning Task Parameters

#### objective
- binary:logistic
- multi:softmax
- multi:softprob
- reg:linear

#### eval_metric
- The default values are rmse for regression and error for classification.
- Typical values are:
 - rmse – root mean square error
 - mae – mean absolute error
 - logloss – negative log-likelihood
 - error – Binary classification error rate (0.5 threshold)
 - merror – Multiclass classification error rate
 - mlogloss – Multiclass logloss
 - auc: Area under the curve





### General Approach for Parameter Tuning
- [example](https://github.com/hczheng/Rong360/blob/master/code/xgboost%E8%B0%83%E5%8F%82%E7%A4%BA%E4%BE%8B%E4%BB%A3%E7%A0%81.py)
- [different API train data](https://blog.csdn.net/VitoDi/article/details/60141301)
