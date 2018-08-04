---
layout: post
title:  "Dimensionality Reduction"
date:   2018-07-22 18:43:31 +0800
categories: jekyll update
---





# Dimensionality Reduction

## Principal Component Analysis (PCA)
[wiki_PCA](https://en.wikipedia.org/wiki/Principal_component_analysis)

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





# overfitting
- add number of sample
- cut off number of feature
- regularization
