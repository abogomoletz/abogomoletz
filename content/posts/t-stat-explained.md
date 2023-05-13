---
title: "T-Tests Explained"
date: 2023-01-16T17:10:36Z
draft: true
---

The t-test is a statistical tool used to determine if the difference between the population mean of two groups is significant or if it could have occurred by chance.

There are two types of t-tests: the one-sample t-test and the two-sample t-test. In this post, we will focus on the two-sample t-test, which is used to compare the means of two groups.

## What is a t-test?

A t-test is a statistical test that allows us to compare two groups of data and determine whether there is a significant difference between them. Specifically, it helps us determine whether the difference between the means of the two groups is large enough to be considered statistically significant.

## Types of t-Test

There are two types of t-tests: the one-sample t-test and the two-sample t-test.

The one-sample t-test is used when you have one group of data and want to compare it to a known value or a hypothetical value.

The two-sample t-test is used when you have two independent groups of data and want to compare them.

### Formulas
The formula for the t-test depends on the type of t-test being used.

#### One-Sample t-Test
The formula for the one-sample t-test is:

t = (x̄ - μ) / (s / √n)

Where:

t is the t-statistic
x̄ is the sample mean
μ is the hypothesized population mean
s is the sample standard deviation
n is the sample size

#### Two-Sample t-Test
The formula for the two-sample t-test is:

t = (x̄1 - x̄2) / (s^2pooled * (1/n1 + 1/n2))^0.5

Where:

t is the t-statistic
x̄1 and x̄2 are the sample means of the two groups
s^2pooled is the pooled variance of the two groups
n1 and n2 are the sample sizes of the two groups

## Null and Alternative Hypotheses

In order to conduct a t-test, we need to start with two hypotheses:

- Null hypothesis (H0): This is the hypothesis that there is no significant difference between the means of the two groups. It's essentially the default assumption that we make before we conduct the test.
- Alternative hypothesis (Ha): This is the hypothesis that there is a significant difference between the means of the two groups. It's what we're trying to prove through our test.

In mathematical notation, the null and alternative hypotheses are typically written as follows:

```
H0: μ1 = μ2

Ha: μ1 ≠ μ2
```
Where μ1 is the mean of the first group and μ2 is the mean of the second group.



## T-Statistic

Once we have our hypotheses, we can calculate a t-statistic. The t-statistic is a measure of the difference between the means of the two groups, relative to the variability within each group. In other words, it tells us how far apart the means are in terms of standard deviation units. (t is this difference represented in units of standard error)

The formula for the t-statistic is:

t = (x1 - x2) / (s / sqrt(n))

Where:

x1 is the mean of the first group
x2 is the mean of the second group
s is the pooled standard deviation (a measure of the variability within each group)
n is the total sample size (i.e., the number of participants in both groups combined)


## Degrees of Freedom

In order to determine whether the t-statistic is large enough to be considered statistically significant, we need to know the degrees of freedom. Degrees of freedom are a measure of the amount of information that is available to estimate a parameter. In the case of a t-test, they are calculated as follows:

df = n1 + n2 - 2

Where:

n1 is the sample size of the first group
n2 is the sample size of the second group

# t-test

When you perform a t-test, you are trying to find evidence of a significant difference between the population mean and a hypothesized value. 

Null hypothesis h0: mu =q
Alternative htypothesis h1: mu != 0 

T is this difference represented in units of standard error. 

The greater the magnitude of T, the greater the evidence against the null hypothesis. The closer T is to 0, the more likely there isn't a significant difference.


## The Null and Alternative Hypotheses

The null hypothesis, denoted as `H0`, is a statement that assumes there is no significant difference between the population means of the two groups being compared. The alternative hypothesis, denoted as `H1`, is the opposite of the null hypothesis, assuming that there is a significant difference between the population means of the two groups being compared.

The null and alternative hypotheses are represented as:

```
H0: μ1 - μ2 = 0
H1: μ1 - μ2 ≠ 0
```
Where `μ1` and `μ2` are the population means of the two groups.