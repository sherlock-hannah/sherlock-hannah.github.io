---
layout: post
title:  "Risk Control"
date:   2018-07-09 18:43:31 +0800
categories: jekyll update
---


Isolation Forest

## Description
detect fraud from transaction data


## Metric
TPR = TP / (TP + FN)
FPR = FP / (FP + TN)

TPR1：when FPR=0.001
TPR2：when FPR=0.005
TPR3：when FPR=0.01

Score = 0.4 * TPR1 + 0.3 * TPR2 + 0.3 * TPR3

## Data analysis

### check missing data information

column missing data :

![userdistribution](/pictures/ateccolumnmissing.png)

![userdistribution](/pictures/atectestcolumnmiss.png)

row missing data:

![userdistribution](/pictures/atecrowmiss.png)



#### detect outlier
#### stability analysis of feature




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
