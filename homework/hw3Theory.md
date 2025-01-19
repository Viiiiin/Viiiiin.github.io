---
layout: default
title: Homework3Theory
permalink: /hwTheory3.html
---
# Median as the Minimizer of the Sum of Absolute Deviations

## Statement
The **Median** is defined as the value that minimizes the sum of absolute deviations from all points in a given dataset. Formally, given a set of observations \( x_1, x_2, \ldots, x_n \), the median \( m \) is the solution to the following minimization problem:

$$
\min_c \sum_{i=1}^n |x_i - c|
$$

## Proof (Simplest Version)
1. Let \( x_1, x_2, \ldots, x_n \) be sorted in ascending order.
2. Consider the function \( S(c) = \sum_{i=1}^n |x_i - c| \), which represents the sum of absolute deviations.
3. For \( c < \text{Median}(x) \):
   - Increasing \( c \) will reduce the sum because more terms \( |x_i - c| \) will decrease.
4. For \( c > \text{Median}(x) \):
   - Decreasing \( c \) will reduce the sum for the same reason.
5. Therefore, the sum \( S(c) \) is minimized when \( c \) is the median of the dataset.

## Intuition
The median is a "balance point" such that half of the observations lie below it and half lie above. By placing \( c \) at the median, the positive and negative contributions to the absolute deviations are balanced, resulting in the minimum possible sum.

# Conceptual Ways to Define a "Location" Statistic

## 1. **Mean (Arithmetic Average)**
   - Formula: 
   $$
   \mu = \frac{1}{n} \sum_{i=1}^n x_i
   $$
   - Description: The mean is the balance point where the sum of deviations (differences from \( \mu \)) is zero. It is sensitive to outliers.

## 2. **Median**
   - Formula: The middle value of a sorted list (or the average of the two middle values if \( n \) is even).
   - Description: Minimizes the sum of absolute deviations. More robust to outliers than the mean.

## 3. **Mode**
   - Formula: The value(s) that appear most frequently in a dataset.
   - Description: Represents the most common value. It is useful for categorical data.

## 4. **Geometric Mean**
   - Formula: 
   $$
   \text{GM} = \left(\prod_{i=1}^n x_i\right)^{1/n}
   $$
   - Description: Useful for datasets with values that are products or growth rates. It is less influenced by extremely large values than the arithmetic mean.

## 5. **Harmonic Mean**
   - Formula: 
   $$
   \text{HM} = \frac{n}{\sum_{i=1}^n \frac{1}{x_i}}
   $$
   - Description: Suitable for rates or ratios, such as speed. It gives more weight to smaller values.

## 6. **Trimmed Mean**
   - Formula: Calculated by removing a percentage of the smallest and largest values and then computing the mean of the remaining data.
   - Description: Balances sensitivity to outliers while still being influenced by the central values.

## 7. **Midrange**
   - Formula: 
   $$
   \text{Midrange} = \frac{\min(x) + \max(x)}{2}
   $$
   - Description: Represents the midpoint between the minimum and maximum values. It is highly sensitive to outliers.

# Generalizing Location Statistics

The concept of "location" statistics can be generalized to create an infinite number of measures by varying the method used to summarize the central tendency. Some generalizations include:

## 1. **L\( _p \) Norms**
   - For a given \( p \geq 1 \), the \( L_p \) norm minimizes 
   $$
   \left(\sum_{i=1}^n |x_i - c|^p\right)^{1/p}
   $$
   - Example:
     - \( p = 1 \): The median minimizes the sum of absolute deviations.
     - \( p = 2 \): The mean minimizes the sum of squared deviations.

## 2. **Quantiles**
   - The \( q \)-th quantile minimizes the asymmetric weighted sum of deviations:
     $$
     \min_c \sum_{i=1}^n w_i (x_i - c)
     $$
   - Different quantiles provide insights into various parts of the distribution (e.g., 25th percentile, 75th percentile).

## 3. **M-estimators**
   - Robust estimators that generalize the mean by minimizing a chosen loss function:
     $$
     \sum_{i=1}^n \rho(x_i - c)
     $$
   - Example: Using a Huber function \( \rho \) provides robustness against outliers while retaining sensitivity to central values.

## Infinite Possibilities
By selecting different norms, weights, or loss functions, an infinite number of central tendency measures can be derived. Each definition provides a unique perspective on the "center" of a distribution, tailored to the specific characteristics or outliers present in the data.
