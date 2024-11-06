---
layout: default
title: Homework5
permalink: /homework5
---
# Cauchy-Schwarz Inequality and Statistical Independence Notes

## 1. Cauchy-Schwarz Inequality Proof


The inequality to prove is:
$$
\left(\sum_{i=1}^n a_i b_i\right)^2 \leq \left(\sum_{i=1}^n a_i^2\right)\left(\sum_{i=1}^n b_i^2\right)
$$

## Proof

Consider that for any real number \( t \), the following sum is always non-negative:
$$
\sum_{i=1}^n (a_i + t b_i)^2 \geq 0
$$

Expanding the square gives:
$$
\sum_{i=1}^n \left(a_i^2 + 2t a_i b_i + t^2 b_i^2\right) \geq 0
$$

Rearrange the terms:
$$
\sum_{i=1}^n a_i^2 + 2t \sum_{i=1}^n a_i b_i + t^2 \sum_{i=1}^n b_i^2 \geq 0
$$

Let’s set:
$$
A = \sum_{i=1}^n a_i^2, \quad B = \sum_{i=1}^n b_i^2, \quad C = \sum_{i=1}^n a_i b_i
$$

The inequality then becomes:
$$
A + 2t C + t^2 B \geq 0
$$

This is a quadratic inequality in \( t \) that must hold for all real values of \( t \). For this to be true, the discriminant of the quadratic must be non-positive:
$$
(2C)^2 - 4AB \leq 0
$$

Simplifying, we get:
$$
4C^2 \leq 4AB
$$
or
$$
C^2 \leq AB
$$

Substituting back, we have:
$$
\left(\sum_{i=1}^n a_i b_i\right)^2 \leq \left(\sum_{i=1}^n a_i^2\right)\left(\sum_{i=1}^n b_i^2\right)
$$

This completes the proof of the Cauchy-Schwarz inequality in summation form.


## 2. Independence vs Uncorrelation

### Conceptual Differences

#### Independence
- Definition: $P(A\cap B) = P(A)P(B)$ for any events $A$ and $B$
- For random variables: $F_{X,Y}(x,y) = F_X(x)F_Y(y)$
- Concerns entire joint distribution
- Stronger condition than uncorrelation

#### Uncorrelation
- Definition: $E(XY) = E(X)E(Y)$
- Equivalently: $\text{Cov}(X,Y) = 0$
- Only concerns first two moments
- Weaker condition than independence

### Key Relationships
- Independence $\Rightarrow$ Uncorrelation
- Uncorrelation $\not\Rightarrow$ Independence
- For normal distributions only: Uncorrelation $\Leftrightarrow$ Independence

### Measures

#### Uncorrelation Measures
1. Pearson Correlation Coefficient ($r$)
   $$
   r = \frac{\text{Cov}(X,Y)}{\sigma_X\sigma_Y}
   $$
2. Covariance
   $$
   \text{Cov}(X,Y) = E[(X-\mu_X)(Y-\mu_Y)]
   $$

#### Independence Measures
1. Mutual Information
   $$
   I(X;Y) = \sum_{x}\sum_{y} p(x,y)\log\left(\frac{p(x,y)}{p(x)p(y)}\right)
   $$
2. Chi-square test of independence
3. Kullback-Leibler divergence
   $$
   D_{KL}(P||Q) = \sum_x P(x)\log\left(\frac{P(x)}{Q(x)}\right)
   $$

### Classic Example
Consider $X \sim U[-1,1]$ and $Y = X^2$:
- They are uncorrelated: $\text{Cov}(X,Y) = 0$
- But clearly dependent: $Y$ is a function of $X$
- Shows uncorrelation $\neq$ independence

