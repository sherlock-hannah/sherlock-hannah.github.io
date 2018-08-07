---
layout: post
title:  "Handle Missing data"
date:   2018-07-05 18:43:31 +0800
categories: jekyll update
---
## Count the number of each column

`df.isnull().sum()`

## Fill missing data
```
from sklearn.preprocessing import  Imputer

imp=Imputer(missing_values='NaN',strategy='most_frequent',axis=0)
imp.fit(X)
X=imp.transform(X)
```
