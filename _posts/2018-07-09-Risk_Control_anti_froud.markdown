---
layout: post
title:  "Risk Control"
date:   2018-07-09 18:43:31 +0800
categories: jekyll update
---



## Description
detect fraud from transaction data


## Metric
TPR = TP / (TP + FN)
FPR = FP / (FP + TN)

TPR1：when FPR=0.001
TPR2：when FPR=0.005
TPR3：when FPR=0.01

Score = 0.4 * TPR1 + 0.3 * TPR2 + 0.3 * TPR3

- detect fraud and reduce false positive

```
def scorer(y, pred):
    fpr, tpr, thresholds = roc_curve(y, pred, pos_label=1)
    score = 0.4 * tpr[np.where(fpr>=0.001)[0][0]] + \
            0.3 * tpr[np.where(fpr>=0.005)[0][0]] + \
            0.3 * tpr[np.where(fpr>=0.01)[0][0]]
    print('-----------------------------result------------------------')
    print('fpr_0.001: {0} | fpr_0.005: {1} | fpr_0.01: {2}'.format(tpr[np.where(fpr>=0.001)[0][0]],
                                   tpr[np.where(fpr>=0.005)[0][0]],
                                   tpr[np.where(fpr>=0.01)[0][0]]))
    print('score : {}'.format(score))
    return score
```




## Data analysis

### label distribution
unlabeled ,negative ,positive label ratio

![userdistribution](/pictures/atec_label.png)

when label = 1
![userdistribution](/pictures/label1_day.png)

when label =0
![userdistribution](/pictures/label0_day.png)


### check missing data information

column missing data :

![userdistribution](/pictures/ateccolumnmissing.png)

![userdistribution](/pictures/atectestcolumnmiss.png)

row missing data:

![userdistribution](/pictures/atecrowmiss.png)



#### detect outlier
#### stability analysis of feature
the sum of missing data
![sta_time_atec](/pictures/sta_time_atec2.png)
the mean of value change with the times
![sta_time_atec](/pictures/sta_time_atec1.png)
risk and distribution
![sta_time_atec](/pictures/f24_risk.png)

## Sample
### down sample
make positive : negative ratio is 1:10
### step Sampling
using LR to separate into two part (label :positive and negative )  
- [step_lr](https://openclub.alipay.com/read.php?tid=8868&fid=96)


## feature engineering
### Isolation
- group Isolation
- individual Isolation
- equipment isolation

### high frequency
- count number in 1 or 3 hour ,compare to others ,and rate feature

### feature group
- high liner correlation



## Models
### supervised

### unsupervised

#### Isolation Forest
- [two-step PU Learning](https://openclub.alipay.com/read.php?tid=5864&fid=96)





## Reference
- [Fraud Detection machine learning Models](https://www.zhihu.com/question/30508773/answer/205831957)
- [PPD_RiskControlcompetition](https://github.com/wepe/PPD_RiskControlCompetition)
- [Build A Complete Project In Machine Learning Credit Card Fraud Detection Eduonix](https://www.youtube.com/watch?v=gCWBFyFTxVU)
- [Novelty and outlier Detection](http://scikit-learn.org/stable/modules/outlier_detection.html)
- [ppd_nemo_submit](https://www.kesci.com/apps/home/competition/forum/574a932f874e65042e150ce8)


## Solution
- [solution_1_0.4368](https://openclub.alipay.com/read.php?tid=8927&fid=96)
- [0.4221](https://openclub.alipay.com/read.php?tid=8890&fid=96)
- [solution_rank_1](https://openclub.alipay.com/read.php?tid=8869&fid=96)
- [new_feature_generation](https://openclub.alipay.com/read.php?tid=8956&fid=96)
