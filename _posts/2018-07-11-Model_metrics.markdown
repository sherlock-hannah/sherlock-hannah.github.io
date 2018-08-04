---
layout: post
title:  "Model_metrics"
date:   2018-07-11 18:43:31 +0800
categories: jekyll update
---
![scoring](/pictures/scoring.png)






## sklearn.metrics.accuracy_score
- `sklearn.metrics.accuracy_score(y_true, y_pred, normalize=True, sample_weight=None)`

- [accuracy_score](http://scikit-learn.org/stable/modules/generated/sklearn.metrics.accuracy_score.html)


## sklearn.metrics.f1_score
![precision](/pictures/precision.png)


![recall](/pictures/recall.png)

![f1score_explain](/pictures/f1score_explain.png)
- F1 = 2 * (precision * recall) / (precision + recall)
- [f1_score](http://scikit-learn.org/stable/modules/generated/sklearn.metrics.f1_score.html)
- [sklearn.metrics.precision_recall_fscore_support](http://scikit-learn.org/stable/modules/generated/sklearn.metrics.precision_recall_fscore_support.html)

- error:continuous is not supported :
because y_pred cant be float array .
[Got continuous is not supported error in RandomForestRegressor](https://stackoverflow.com/questions/32664717/got-continuous-is-not-supported-error-in-randomforestregressor)



example,write F1 score by self  

```
is_in = predicted_ui.isin(reference_ui)
true_positive = predict2[is_in]

tp = len(true_positive)
predictedSetCount = len(predict2)
referenceSetCount = len(reference)

precision = tp / predictedSetCount
recall = tp / referenceSetCount

f_score = 2 * precision * recall / (precision + recall)

tp = recall * referenceSetCount
predictedSetCount = tp / precision

print('%.8f%% %.8f %.8f %.0f %.0f' %
      (f_score * 100, precision, recall, tp, predictedSetCount))

```





## Metric: ROC AUC

![Mean squared logarithmic error](/pictures/ROC-curve.png)








## Mean squared logarithmic error_sklearn

![Mean squared logarithmic error](/pictures/Mean squared logarithmic error.png)

[Mean squared logarithmic error_sklearn](http://scikit-learn.org/stable/modules/model_evaluation.html#mean-squared-error)

```
from sklearn.metrics import mean_squared_log_error
mean_squared_log_error(y_true, y_pred)
```
