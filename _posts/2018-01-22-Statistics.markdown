---
layout: post
title:  "Statistics"
date:   2018-01-22 18:43:31 +0800
categories: jekyll update
---
Used to make decisions
## Decriptive statistics
- 1.range,variance,standand deviation, standand error
- 2.skewness positive numbers means it's right skewed.
    negative numbers means it's left skewed
- 3. Histogram: look at the tail. If one tail is longer than another, the distribution is skewed. just need 1D data can contrive histogram because of y axis is becomes the count of data ,and bar chart need 2D data.
- 4.correlation
 Correlation values may range from -1 to 1, where 1 would mean the two features are perfectly positively correlated and have identical slopes for all values. -1 would mean they are perfectly negatively correlated, and have a negative slope for one another, again being linear.
mention spurious relationship
- 4.p value
- 5.T-test ;two-sample t-test;paired t-test
- 6.analysis of variance(ANOVA)
- 7.regression standandlise regression coeffient

## Basic Probability
- independent event : Two events A and B are independent if and only if Prob(A and B) = Prob(A) * Prob(B)
- mutually exclusive:A and B are mutually exclusive,We know Prob(A and B) = 0. For independence, we then need Prob(A)* Prob(B) = 0.
- Conditional Probability:P(A|B)=P(A ∩ B) / P(B)
- Law of Total Probability(find a chance of event by adding up all rhe mutually exclusive ways event can happen):P(A) = ∑ P(A|Bi) * P(Bi)

## Random variable
- Discrete Random Variable
- Continuous Random Variable
is described by a probability density function (PDF)
- Binomial Random Variable
Each trial has two outcomes:Success and Failure
Outcomes of trials are independent
`BINOM.DIST.RANGE(n,p,s1,s2)`
Probability of between s1 and s2,successes (inclusive)

- Possion Random Variable

- Normal Random Variable

## Central Limit Theorem
Add together 30 or more independent random variables, Even if none of the individual random variables are normal,the sum of the random variables will be normal.

## Z Scores
z  = (x-μ)/σ
Any Z score >=+2 or <=-2 is an outlier

## Samples and Sample Statistics
Suppose a population has N individuals and we want to take a sample of size n. The sample is a simple random sample if each set of n individuals has the same chance of being chosen.

bias
- Selection bias occurs when each item in population does not have same chance of being chosen in sample
- Publication Bias occurs because drug studies with positive results are more likely to be published than negative results.
- Survivorship Bias occurs when part of a population disappears.
- Response Bias occurs when a small fraction of those sampled respond and the respondents may not be representative of the population.

sample mean
- xbar=(x1+x2+….,xn)/n
- The Standard Deviation of  Xbar is σ/sqrt(n)

Standard Normal (often called Z)is a normal random variable with mean =0 and standard deviation=1

## Confidence interval
True Interpretation of 95% CI Take 100 samples compute 100 95% CI around 95 will contain the population mean.

## Blyth Confidence Interval

| Success    | Lower                |Upper
| :--------- | :-------------       |
| 0          | 0                    |1-alpha^(1/n)
| 1          |1-(1-0.5*alpha)^(1/n) |1-(0.5*alpha)^(1/n)
| N          |(alpha)^(1/n)         |1

## Sample Size
n = (1.96σ/E)^2
Sample Size for Population Proportion E=.03
n= 1.96^2/4E^2

## Finite Correction Factor
SQRT((N-n)/(N-1))
In general a more accurate sample size formula
N*N0/(N+N0-1)

## Hypothesis testing
1. state hypothesis
H0 =null hypothesis H1= alternative hypothesis
2. analysis plan
T-test
3. gather data
4. analyze
mean score ,T score
5. interpret
if the statistics Probability is less than the significance level ,the null hypothesis is rejected











## problems:
- 1.right skewed
- 2.liner regression


## Additional reading
[Statistics Primer : A Brief Overview of Basic Statistical and Probability Principles](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/d2dce71b2552f8d45d47102929821e87/asset-v1:Microsoft+DAT222x+1T2018+type@asset+block/Statistics_Overview_for_Essentials_Course-Updated.pdf)
