---
layout: post
title:  "Machine learning"
date:   2018-02-23 18:43:31 +0800
categories: jekyll update
---

supervised learning
unsupervised learning

## Classification

- statistics learning theory

### logistic regression
- logistic regression formula

- loss functions




- maximum likelihood perspective
- evaluation method for classifier
confusion matrix
misclassification error
(FN+FN)/N
- ROC curves
- ROC curves algorithm
- Creating a Classifier with Python


## Regression
### LinearRegression
- one of the performance Statistics used in adjust R
- outlier
y= w0+w1x1+w1x2+ ... + wnxn

[sklearn.linear_model.LinearRegression](http://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html)
## Clustering
- RandomForest


## Dimensionality Reduction
### Principal Component Analysis (PCA)
(unsupervised learning algorithm)

avoid [The curse of dimensionality](https://en.wikipedia.org/wiki/Curse_of_dimensionality)
1. standandlise variable
2. accesses dataset's covariance structure and eigenvectors to compute the best unique features

[Principal Component Analysis notebook](https://yoyoyohamapi.gitbooks.io/mit-ml/content/%E7%89%B9%E5%BE%81%E9%99%8D%E7%BB%B4/articles/PCA.html)
```
from sklearn.decomposition import PCA
 pca = PCA(n_components=2, svd_solver='full')
 pca.fit(df)
PCA(copy=True, n_components=2, whiten=False)

T = pca.transform(df)
```
- `n_components` the number of  dimensions you want keep
- `svd_solver` dictates if a full singular value decomposition should be preformed on your data
- principal component feature space with the `.transform()` method.
- `whiten`When True (False by default) the components_ vectors are multiplied by the square root of n_samples

[parameter](sklearn.decomposition.PCA)











## Improving Machine Learning Models


## Another Reading
[gitbook](https://legacy.gitbook.com/book/yoyoyohamapi/mit-ml/details)

[scikit-learn-chinese](http://sklearn.apachecn.org/cn/0.19.0/)

[scikit-learn](http://scikit-learn.org/stable/index.html)


## problems
1. full singular value decomposition??
