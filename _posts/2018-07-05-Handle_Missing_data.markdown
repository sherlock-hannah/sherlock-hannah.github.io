---
layout: post
title:  "Handle Missing data"
date:   2018-07-05 18:43:31 +0800
categories: jekyll update
---
## Count the number of each column

`df.isnull().sum()`

## Fill missing data
- Continuous feature
 - when distribution is normal distribution,then fill missing data using mean.
 - when distribution is long tail distribution,then fill missing data using median.
- Discrete feature
  - use mode 

```
from sklearn.preprocessing import  Imputer

imp=Imputer(missing_values='NaN',strategy='most_frequent',axis=0)
imp.fit(X)
X=imp.transform(X)

```
