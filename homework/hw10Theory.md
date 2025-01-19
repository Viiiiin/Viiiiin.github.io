---
layout: default
title: Homework10Theory
permalink: /hwTheory10.html
---
# Concepts in Statistics and Measure Theory

## 1. Sampling Mean and Variance

The **sample mean** and **sample variance** are fundamental concepts in statistics, representing the average and the variability of a sample, respectively. They are used to estimate the corresponding population parameters.

### 1.1 Mean
The sample mean is defined as:  
$$\bar{X} = \frac{1}{n} \sum_{i=1}^n X_i,$$  
where \( X_1, X_2, \dots, X_n \) are the observed values of a random sample of size \( n \).

### 1.2 Variance
The sample variance measures the dispersion of the data around the sample mean and is given by:  
$$S^2 = \frac{1}{n-1} \sum_{i=1}^n (X_i - \bar{X})^2.$$

### 1.3 Features of Their Distributions
1. **Sampling Distribution of the Mean**:  
   If the population has mean \( \mu \) and variance \( \sigma^2 \), the sampling distribution of the mean for a sample of size \( n \) has:
   $$\text{Mean} = \mu, \quad \text{Variance} = \frac{\sigma^2}{n}.$$
   By the Central Limit Theorem (CLT), the sampling distribution of the mean approaches a normal distribution as \( n \to \infty \), regardless of the population's original distribution.

2. **Sampling Distribution of the Variance**:  
   If the population is normally distributed, the sample variance \( S^2 \) follows a scaled \( \chi^2 \)-distribution:
   $$\frac{(n-1)S^2}{\sigma^2} \sim \chi^2_{n-1}.$$

---

## 2. Lebesgue–Stieltjes Integration

Lebesgue–Stieltjes integration generalizes the Riemann integral and is widely used in probability theory and measure theory. It integrates a function \( f \) with respect to a function \( g \), where \( g \) is monotonically increasing.

### 2.1 Definition
For a function \( f \) and a monotonically increasing function \( g \), the Lebesgue–Stieltjes integral is defined as:
$$\int_a^b f(x) \, dg(x).$$

If \( g(x) \) is differentiable, then:
$$\int_a^b f(x) \, dg(x) = \int_a^b f(x) g'(x) \, dx,$$  
where \( g'(x) \) is the derivative of \( g(x) \).

### 2.2 Applications

#### Probability Theory
In probability, the function \( g(x) \) is often a cumulative distribution function (CDF), denoted by \( F(x) \). For a random variable \( X \) with CDF \( F(x) \), the expected value of a function \( h(X) \) is:
$$\mathbb{E}[h(X)] = \int_{-\infty}^\infty h(x) \, dF(x).$$

#### Measure Theory
In measure theory, the Lebesgue–Stieltjes integral connects measures with integration. If \( \mu \) is a measure induced by \( g(x) \), then:
$$\int f \, d\mu = \int f(x) \, dg(x).$$

---

## 3. Measure Theory

Measure theory formalizes the concept of size, length, area, and probability. A **measure** \( \mu \) is a function that assigns a non-negative value to subsets of a given set \( \Omega \), satisfying the following properties:

1. **Non-negativity**: \( \mu(A) \geq 0 \) for any measurable set \( A \).
2. **Null Empty Set**: \( \mu(\emptyset) = 0 \).
3. **Countable Additivity**: For a countable sequence of disjoint sets \( A_1, A_2, \dots \),
   $$\mu\left(\bigcup_{i=1}^\infty A_i\right) = \sum_{i=1}^\infty \mu(A_i).$$
