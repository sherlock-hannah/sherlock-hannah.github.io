---
layout: post
title:  "Statistics"
date:   2018-01-22 18:43:31 +0800
categories: jekyll update
---


# Tips

Correlation Doesn’t Equal Causation

# Decriptive statistics
- 1.range,variance,standand deviation, standand error

- 2.skewness positive numbers means it's right skewed.
    negative numbers means it's left skewed

- 3.Histogram: look at the tail. If one tail is longer than another, the distribution is skewed. just need 1D data can contrive histogram because of y axis is becomes the count of data ,and bar chart need 2D data.

- 4.correlation

 Correlation values may range from -1 to 1, where 1 would mean the two features are perfectly positively correlated and have identical slopes for all values. -1 would mean they are perfectly negatively correlated, and have a negative slope for one another, again being linear.
mention spurious relationship

- 6.analysis of variance(ANOVA)
 - [How To Calculate and Understand Analysis of Variance (ANOVA) F Test](https://www.youtube.com/watch?v=-yQb_ZJnFXw)

- 7.regression standandlise regression coeffient

# Basic Probability
## sample space
the set of all possible Outcomes.

![count_sample](../pictures/count_sample.png)

![sort_sample](../pictures/sort_sample.png)

## independent event :
Two events A and B are independent if and only if Prob(A and B) = Prob(A) * Prob(B)

## mutually exclusive
A and B are mutually exclusive,We know Prob(A and B) = 0. For independence, we then need Prob(A)* Prob(B) = 0.


## Conditional Probability
P(A|B)=P(A ∩ B) / P(B)


P(A ∩ B)

![eventA_eventB](../pictures/eventA_eventB.png)

## Law of Total Probability
(find a chance of event by adding up all rhe mutually exclusive ways event can happen):

P(A) = ∑ P(A|Bi) * P(Bi)

## Blyth

![blyth](../pictures/blyth.png)


![blyth_formula](../pictures/blyth_formula.png)





# Random variable
## Discrete Random Variable
### Binomial Random Variable

- Each trial has two outcomes:Success and Failure
Outcomes of trials are independent

![Binomial](../pictures/Binomial.png)

- example in excel:

`BINOM.DIST.RANGE(n,p,s1,s2)`
Probability of between s1 and s2,successes (inclusive)

`P(x ≥ 4) = 1–BINOM.DIST(3, 10, 1/6, TRUE)`
calculate p value

### poisson Random Variable

- expresses the probability of a given number of events occurring in a fixed interval of time or space if these events occur with a known constant rate and independently of the time since the last event

![Binomial](../pictures/Possion.png)
u is mean of 



- extreme of Binomial distribution.when n is big,p is small,Binomial distribution is similar to poisson distribution

- [Poisson distribution](https://en.wikipedia.org/wiki/Poisson_distribution)

## Continuous Random Variable








- Normal Random Variable

## Central Limit Theorem
Add together 30 or more independent random variables, Even if none of the individual random variables are normal,the sum of the random variables will be normal.

## Z Scores
z  = (x-μ)/σ
Any Z score >=+2 or <=-2 is an outlier

## Samples and Sample Statistics
Suppose a population has N individuals and we want to take a sample of size n. The sample is a simple random sample if each set of n individuals has the same chance of being chosen.

### bias
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

- Lower One-Sided Alternative:
H0: µ = $79,263 or µ>=$79,263 Ha: µ<$79,263.
- Upper One-Sided Alternative:
H0: p <=.10 Ha: p >.10
- Two-Tailed Alternative
H0: Annual Variance Stock Returns = Annual Variance on Bond Returns.
Ha: Annual Variance Stock Returns ≠ Annual Variance on Bond Returns.




## Type 1 and type 2 errors
1. Reject H0 given H0 True.

 We let α= Probability of making a Type I Error. α is often called the level of significance of the test.

2. H0 is wrong ,but be accepted

- Critical Region
The critical region is the range of values for a sample statistic that results in rejection of H0

## One Sample Z-Test
One Sample Z-Test Test hypothesis about µ; Variance population  known Use when n>=30 because xbar will be normal by CLT.
![ztest](../pictures/ztest.png)
P Value<=α if and only if we reject H0.
P-Value>α if and only if we accept H0.

## One Sample T-Test
### T Random Variable
If population is normal with mean µ and standard deviation is unknown then (xbar-µ) /(s/sqrt(n)).

s= sample standard deviation

n = sample size
### Critical Region
Critical Region:

![ttest](../pictures/ttest.jpg)

### P-Values

![pvalue](../pictures/pvalue.png)

- A small p-value (typically ≤ 0.05) indicates strong evidence against the null hypothesis, so you reject the null hypothesis.

- A large p-value (> 0.05) indicates weak evidence against the null hypothesis, so you fail to reject the null hypothesis.

The P-value may also be interpreted as the probability of observing (given H0 is true) a value of the test statistic at least as extreme as the observed value of the test statistic.

### T.INVERSE Function
excel:
`t.dist(x,freedom,True)`'
`t.inv(α，freedom)`
## Single Sample Test for Population Proportion
Right Tailed Test:

`BINOM.DIST.RANGE(trials,Pzero,successes,trials)`

Left Tailed Test

`BINOM.DIST.RANGE(trials,Pzero,0,successes)`

Two Tailed Test

`2*MIN(Lefttailedpvalue,Righttailedpvalue)`

p-value is less than or equal to α，then reject H0

## Testing Equality of Variances

USE F.TEST FUNCTION TO GET P-VALUE,
PVALUE<=ALPHA Reject Null
`F.TEST(F5:F18,G5:G22)`

## Four Types of Tests
- Two Sample Z-Test

Large sample size (n>=30)

P-Value =0 so reject null hypothesis


- Equal Variance T-Test

Small Sample size (n<30)

IF it is normal distribution,use `SKEW()` `KURT()`

- Unequal Variance T-Test

Small Sample size (n<30)

- Idea of Pairing Samples

excel:data analysis

- T-Test Paired Two Sample for Means

libre office calc:data -T-Test Paired Two Sample for Means

if p value is big ,then accept H0.



## Contingency Table and Hypothesis of Independence
CHI SQUARE TEST FOR INDEPENDENCE

H0:independent;H1:dependent

if p value >0.05,then accept h0.
- Excel : `CHISQ.DIST.RT(sum,degree of freedom)`

- Degrees of Freedom:(R-1) * (C-1)  

- sum: sum of (Oij-Eij)^2/Eij






## Problems:
- 1.right skewed
- 2.liner regression


## Additional reading
- [Statistics Primer : A Brief Overview of Basic Statistical and Probability Principles](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/d2dce71b2552f8d45d47102929821e87/asset-v1:Microsoft+DAT222x+1T2018+type@asset+block/Statistics_Overview_for_Essentials_Course-Updated.pdf)
- [Crash Course Statistics](https://www.youtube.com/watch?v=zouPoc49xbk&list=PL8dPuuaLjXtNM_Y-bUAhblSAdWRnmBUcr)
- [basic statistics](https://www.jianshu.com/p/76afb7193fa5)
