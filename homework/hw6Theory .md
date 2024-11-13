---
layout: default
title: Homework6Theory
permalink: /hwTheory6.html
---
# Fundamental Theorem of Calculus and Its Relationship with Density Functions and Cumulative Distribution Functions (CDFs)

The **Fundamental Theorem of Calculus** connects the concepts of differentiation and integration, providing an essential tool for understanding probability density functions and cumulative distribution functions (CDFs) in probability theory.

## Fundamental Theorem of Calculus

The Fundamental Theorem of Calculus has two main parts:

1. **First Part:** If \( F(x) \) is defined as the integral of a function \( f(t) \) from a fixed point \( a \) to \( x \), then \( F(x) \) is differentiable, and its derivative is equal to \( f(x) \):
   $$
   F(x) = \int_a^x f(t) \, dt \Rightarrow F'(x) = f(x).
   $$

2. **Second Part:** If \( f(x) \) is continuous on an interval \([a, b]\) and \( F \) is an antiderivative of \( f \), then:
   $$
   \int_a^b f(x) \, dx = F(b) - F(a).
   $$

## Application to Density Functions and Cumulative Distribution Functions (CDFs)

In probability theory, the relationship between **density functions** and **cumulative distribution functions** reflects the Fundamental Theorem of Calculus.

### Cumulative Distribution Function (CDF)

The cumulative distribution function \( F(x) \) of a random variable \( X \) is defined as:
$$
F(x) = P(X \leq x) = \int_{-\infty}^x f(t) \, dt,
$$
where \( f(x) \) is the **probability density function** (PDF) of \( X \), assuming \( X \) is a continuous random variable.

This definition directly reflects the first part of the Fundamental Theorem of Calculus:
- \( F(x) \) represents the area under the curve of \( f(t) \) from \(-\infty\) to \( x \).
- The CDF \( F(x) \) is an antiderivative of the PDF \( f(x) \), so the derivative of \( F(x) \) is \( f(x) \):
  $$
  F'(x) = f(x).
  $$

Thus, if we know the PDF \( f(x) \), we can calculate the CDF \( F(x) \) by integrating. Conversely, if we have the CDF \( F(x) \), we can find the PDF \( f(x) \) by differentiating:
$$
f(x) = \frac{d}{dx} F(x).
$$

### Intuitive Interpretation

- The CDF \( F(x) \) gives the probability that the random variable \( X \) takes on a value less than or equal to \( x \), calculated by integrating the PDF up to \( x \).
- The PDF \( f(x) \), obtained by differentiating the CDF, provides information on the relative likelihood that \( X \) takes on a specific value \( x \), representing the “rate of accumulation” of probability at \( x \).

