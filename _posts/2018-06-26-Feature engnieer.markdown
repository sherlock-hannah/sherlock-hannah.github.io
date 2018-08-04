---
layout: post
title:  "Feature engnieer"
date:   2018-06-26 18:43:31 +0800
categories: jekyll update
---
# Encoding Categorical Variables

## Label encoding
- assign each unique category in a categorical variable with an integer.
- No new columns are created.

```
le = LabelEncoder()
le.fit(app_train[col])
# Transform both training and testing data
app_train[col] = le.transform(app_train[col])
```


## one_hot encoding
- create a new column for each unique category in a categorical variable.
- can plus PCA

```
app_train = pd.get_dummies(app_train)
app_test = pd.get_dummies(app_test)

print('Training Features shape: ', app_train.shape)
print('Testing Features shape: ', app_test.shape)
```
## Aligning Training and Testing Data

To remove the columns in the training data that are not in the testing data, we need to align the dataframes

```
train_labels = app_train['TARGET']
app_train, app_test = app_train.align(app_test, join = 'inner', axis = 1)
app_train['TARGET'] = train_labels

```




# Create feature
- rank feature
- Discrete feature
- count feature
- category feature
- cross feature
- String feature transform

# Feature Selection


## feature importances

- random forest
- XGBoost






# Another Reading

[use sklearn to feature engnieer](http://www.cnblogs.com/jasonfreak/p/5448385.html)
