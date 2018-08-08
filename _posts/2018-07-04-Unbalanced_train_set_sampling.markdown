---
layout: post
title:  "Unbalanced train_set sampling "
date:   2018-07-04 18:43:31 +0800
categories: jekyll update
---
use sklearn spilt train and test dataset

```
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(features, outcomes, test_size=0.2, random_state=42)
```

# Random Under-Sampling

`pandas.DataFrame.sample()`

example:

```
trainsample1 = train_set[train_set['label']==0].sample(frac=0.2,random_state=999)
trainsample2 = train_set[train_set['label']==1]
trainsample = pd.concat([trainsample1,trainsample2])
```
[pandas.DataFrame.sample](https://pandas.pydata.org/pandas-docs/version/0.22/generated/pandas.DataFrame.sample.html)
- n :
Number of items from axis to return. Cannot be used with frac. Default = 1 if frac = None.

- frac :
Fraction of axis items to return. Cannot be used with n.

- replace :
Sample with or without replacement. Default = False.

## EasyEnsemble

![EasyEnsemble](/pictures/EasyEnsemble.jpg)


## BalanceCascade


# Random Over-Sampling



## SMOTE(Synthetic Minority Over-sampling Technique):

it is also a type of oversampling but in this we will make the synthetic example of Minority data and will give as a balanced data

![smote](/pictures/smote.png)

# References
- [class-imbalance](https://zhuanlan.zhihu.com/p/36381828)
