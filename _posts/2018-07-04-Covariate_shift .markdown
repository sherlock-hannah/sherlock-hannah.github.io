---
layout: post
title:  "How to handle with covariate shift "
date:   2018-07-04 18:43:31 +0800
categories: jekyll update
---

![covariate shift](../pictures/covariate shift.png)
# How (dis)similar are train and test data
[use auc to estimate whether different distribution between train and test data](https://towardsdatascience.com/how-dis-similar-are-my-train-and-test-data-56af3923de9b)

If AUC score greater than 0.8 implies strong covariate shift between train and test.

# solution


## Dropping of drifting features

use random forest to rank the Importance of features

```
forest = ExtraTreesClassifier(n_estimators=250,
                              random_state=0,n_jobs=-1)
forest.fit(x_train, y_train)
importances = forest.feature_importances_
indices = np.argsort(importances)[::-1]
for f in range(x_train.shape[1]):
    print("%2d) %-*s %f" % (f + 1, 30, indices[f]+1, importances[indices[f]]))
```



## Importance weight using Density Ratio Estimation






## Outlier Detection

- [Novelty and outlier Detection](http://scikit-learn.org/stable/modules/outlier_detection.html)
