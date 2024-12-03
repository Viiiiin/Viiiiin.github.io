---
layout: default
title: Homework8Theory
permalink: /hwTheory8.html
---


# Properties of the Sampling Mean and Variance

## Sampling Mean (\( \bar{X} \))
1. **Unbiasedness**:  
   The sampling mean is an unbiased estimator of the population mean \( \mu \):  
   $$  
   \mathbb{E}[\bar{X}] = \mu  
   $$

2. **Consistency**:  
   As the sample size (\( n \)) increases, \( \bar{X} \) converges in probability to \( \mu \):  
   $$  
   \bar{X} \xrightarrow{p} \mu  
   $$

3. **Distribution**:  
   For large \( n \), the sampling mean is approximately normally distributed, regardless of the population distribution (Central Limit Theorem):  
   $$  
   \bar{X} \sim \mathcal{N}\left(\mu, \frac{\sigma^2}{n}\right)  
   $$

---

## Sampling Variance (\( S^2 \))
1. **Unbiasedness**:  
   The sample variance is an unbiased estimator of the population variance \( \sigma^2 \):  
   $$  
   \mathbb{E}[S^2] = \sigma^2  
   $$

2. **Consistency**:  
   The sample variance converges to the population variance as \( n \) increases:  
   $$  
   S^2 \xrightarrow{p} \sigma^2  
   $$

3. **Relation to the Mean**:  
   The sample variance measures the average squared deviation of data points from the sample mean:  
   $$  
   S^2 = \frac{1}{n - 1} \sum_{i=1}^n (X_i - \bar{X})^2  
   $$

---

# Law of Large Numbers (LLN)

The LLN states that as the sample size \( n \) increases, the sample mean \( \bar{X} \) approaches the population mean \( \mu \):  
$$  
\lim_{n \to \infty} \mathbb{P} \left( \left| \frac{1}{n} \sum_{i=1}^n X_i - \mu \right| < \epsilon \right) = 1 \quad \forall \epsilon > 0  
$$

## Implications
- The sample mean stabilizes as the number of observations increases.
- Variability of \( \bar{X} \) diminishes with larger sample sizes.

---

# Illustration of LLN

## Example 1: Coin Toss
For a fair coin toss:
- Let \( X_i = 1 \) for heads and \( X_i = 0 \) for tails.
- The population mean \( \mu = 0.5 \).  
As \( n \to \infty \), the proportion of heads (\( \bar{X} \)) converges to 0.5.

## Example 2: Cybersecurity Event Rates
Suppose \( X_i \) represents the outcome of a login attempt (1 for success, 0 for failure).  
- \( \bar{X} \) estimates the success rate.
- As the number of attempts increases, \( \bar{X} \to \text{true success rate} \).

---

# Applications in Cybersecurity

### 1. Intrusion Detection
- LLN helps establish a baseline for average login attempts or packet rates.
- Deviations signal potential anomalies like brute force or DDoS attacks.

### 2. False Positives Estimation
- Using historical data, \( \bar{X} \) estimates false positive rates for intrusion detection systems (IDS).  
- Larger samples improve reliability of predictions.

### 3. Cryptography Entropy Analysis
- LLN ensures the average entropy of cryptographic keys stabilizes over repeated sampling.
- Variability in entropy could signal weaknesses in key generation.

### 4. Risk Assessment
- Repeated sampling of exploit success rates provides reliable risk estimates.
- Larger datasets improve precision for vulnerability analysis.

---

# Visualizing LLN

1. **Simulations**:
   - Generate random samples from distributions (e.g., normal, binomial).
   - Plot \( \bar{X} \) converging to \( \mu \) as \( n \) increases.

2. **Cybersecurity Example**:
   - Use logs or network traffic to compute averages over time (e.g., packet size, login success rate).
   - Show convergence to baseline under normal conditions and deviations during attacks.
