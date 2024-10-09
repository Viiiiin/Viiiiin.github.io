---
layout: default
title: Homework1Theory
permalink: /homework1.html
---
# Q.1
### Population
In statistics, a population refers to the total number of statistical units that share at least one common characteristic of interest in a statistical analysis.

For example, a population could be defined as all residents of a particular city who are employed. Since it is usually impractical to gather data from every single individual in the population, a sample is often selected, allowing for the analysis of a subset that represents the larger group.

There are different sampling methods to choose from when selecting a sample. For smaller populations, such as all employees in a specific company, a full population survey could be conducted, which is referred to as a census.

A key principle for all populations is the necessity of clearly defined criteria regarding who is included. For instance, when defining a group like “all employed residents of a city,” one would need to specify whether only full-time employees are included or if part-time and self-employed individuals also count. Similarly, it's important to determine if temporary residents are considered part of the population or only those with permanent residency.


### Statistical units
The basic assumption in statistics is that the analysis is conducted on sets of elements known as "statistical units," and that these units can be described through attributes, which are referred to as "characteristics."

Statistical units can represent any kind of objects or events, whether real or virtual, such as natural phenomena (e.g., rainfall), the outcomes of measurement programs, dice rolls, individuals (such as Italian citizens), groups of people (e.g., households), or social and economic phenomena (like marriages, employment relationships, or bank transactions), among many others.

The "characteristics" of these units will vary depending on what is being analyzed. For individuals, relevant characteristics might include gender, income, or occupation. For "bank transactions," on the other hand, meaningful characteristics could be the type of transaction, the bank involved, the amount of money, the currency, or the maturity date of the transaction.

### Distribution
A statistical distribution, or probability distribution, describes how values are distributed for a field. In other words, the statistical distribution shows which values are common and uncommon.

There are many kinds of statistical distributions, including the bell-shaped normal distribution. We use a statistical distribution to determine how likely a particular value is. For example, if we have a chi-square value, we can use the chi-square distribution to determine how likely this chi-square value is.


### Frequency

In statistics, the term "frequency" refers to the number of times a particular event or outcome occurs within a data set. It can be expressed in various forms: absolute, relative, and percentage.

1. **Absolute Frequency**: The absolute frequency, \\(f_i\\), of a statistical unit is the actual count of occurrences for a given characteristic in the dataset. For example, if 10 out of 100 people surveyed own a car, the absolute frequency of car owners is 10.

2. **Relative Frequency**: The relative frequency, \\(f'_i\\), is the ratio of the absolute frequency to the total number of observations, \\(N\\), in the dataset. It is defined by the formula:
   
   $$
   f'_i = \frac{f_i}{N}
   $$
   
   Using the previous example, if 10 out of 100 people own a car, the relative frequency is:
   
   $$
   f'_i = \frac{10}{100} = 0.1
   $$

3. **Percentage Frequency**: The percentage frequency, \\(f''_i\\), expresses the relative frequency as a percentage. It is calculated by multiplying the relative frequency by 100:

   $$
   f''_i = f'_i \times 100
   $$
   
   For the car ownership example, the percentage frequency is:

   $$
   f''_i = 0.1 \times 100 = 10\%
   $$

In summary, frequency analysis helps in understanding the distribution of characteristics across the dataset, providing insights into how often certain outcomes occur relative to the whole population.


# Q.2
### 

In statistics, the **mean** is a measure of central tendency that identifies the value around which all other data points tend to cluster. Mathematically, the mean minimizes the sum of the squared differences between itself and each data point. This is because it balances the distribution of data, ensuring that the sum of the deviations to the left of the mean equals the sum of the deviations to the right.

The idea of the mean can be visualized as finding a point that balances the data set. If we imagine the data points on a number line, the arithmetic mean is the point where the total "weight" of the data is balanced, making it a center of mass.

#### Arithmetic Mean

The **arithmetic mean** is the most commonly used mean and is calculated by summing all values and dividing by the number of values:

$$
\bar{x} = \frac{1}{n} \sum_{i=1}^{n} x_i
$$

Where:
- \\(\bar{x}\\) is the arithmetic mean.
- \\(x_i\\) represents each data point.
- \\(n\\) is the total number of data points.

#### Weighted Mean

The **weighted mean** takes into account the relative importance or frequency of each data point. If different values have different weights \\(w_i\\), the weighted mean is calculated as:

$$
\bar{x}_w = \frac{\sum_{i=1}^{n} w_i x_i}{\sum_{i=1}^{n} w_i}
$$

This formula emphasizes certain data points more than others, based on their assigned weights.

#### Cumulative Mean

The **cumulative mean** is a running average that incorporates each new data point progressively. For each new value, the cumulative mean is updated as:

$$
\bar{x}_k = \frac{1}{k} \sum_{i=1}^{k} x_i
$$

or recursively:

$$
\bar{x}_k = \bar{x}_{k-1} + \frac{x_k - \bar{x}_{k-1}}{k}
$$

Where:
- \\(\bar{x}_k\\) is the mean after the \\(k\\)-th data point is added.
- \\(x_k\\) is the \\(k\\)-th data point.
- \\(k\\) is the number of data points considered so far.

### Mathematical Interpretation

In a symmetrical distribution, the mean has an important geometric property: it equalizes the total distances on both sides. In other words, the sum of the deviations from the mean on the left side is equal to the sum of the deviations on the right side. This makes the mean a "balance point" of the data set.

For example, if we take the set \\(2, 4, 6\\), the arithmetic mean is \\(4\\). The deviation of 2 from the mean is -2, while the deviation of 6 is +2. The sum of these deviations is zero, confirming the balancing nature of the mean.

### Derivation
The derivative is primarily used when there is some varying quantity, and the rate of change is not constant. The derivative is used to measure the sensitivity of one variable (dependent variable) with respect to another variable (independent variable).

### Floating-point
Floating-point arithmetic is considered an esoteric subject by many people. This is rather surprising because floating-point is ubiquitous in computer systems. Almost every language has a floating-point datatype; computers from PCs to supercomputers have floating-point accelerators.
#### Floating-Point Representation of Real Numbers

The most common representation of real numbers in computers is the **floating-point representation**, which uses a base (typically 2 or 10) and a precision \( p \). For example, the number \( 0.1 \) can be represented as 

\[
1.00 \times 10^{-1}
\]

with base 10 and precision 3, while in binary with base 2 and precision 24, \( 0.1 \) cannot be represented exactly and is approximated by an infinite binary fraction.

A floating-point number is generally expressed as 

\[
\pm d_0 . d_1 d_2 \ldots d_{p-1} \times \beta^e
\]

where \( d_0 . d_1 d_2 \ldots d_{p-1} \) is the **significand** with \( p \) digits, and \( e \) is the exponent. The range between the maximum and minimum exponents (\( e_{max} \) and \( e_{min} \)) determines the range of representable numbers. 

Some real numbers cannot be exactly represented for two reasons: either they have an infinite binary representation (e.g., \( 0.1 \) in base 2) or they are out of the range supported by the exponents.

Floating-point representation can be **normalized** (e.g., \( 1.00 \times 10^{-1} \) is normalized, while \( 0.01 \times 10^{1} \) is not). Normalization makes the representation unique but introduces the issue of being unable to represent zero exactly without additional mechanisms.

# Rounding errors
Squeezing infinitely many real numbers into a finite number of bits requires an approximate representation. Although there are infinitely many integers, in most programs the result of integer computations can be stored in 32 bits. In contrast, given any fixed number of bits, most calculations with real numbers will produce quantities that cannot be exactly represented using that many bits. Therefore the result of a floating-point calculation must often be rounded in order to fit back into its finite representation. This rounding error is the characteristic feature of floating-point computation

# Catastrophic Cancellation

**Catastrophic cancellation** occurs in numerical computations when significant digits are lost due to the subtraction of nearly equal numbers. This loss of precision can lead to results that have large relative errors, undermining the accuracy of computations.

## Example of Catastrophic Cancellation

Consider two numbers \( a \) and \( b \) that are very close in value, such as:

\[
a = 1.0000001
\]
\[
b = 1.0000000
\]

When we compute \( a - b \), the result is:

\[
c = a - b = 0.0000001
\]

However, if these numbers are represented in a computer with limited precision, they might be approximated as:

\[
a \approx 1.0
\]
\[
b \approx 1.0
\]

Then, the subtraction yields:

\[
c \approx 0.0
\]

This shows that the actual result, which should be \( 0.0000001 \), is lost, leading to significant relative error.


# Numerical Solution

In the context of Donald Knuth's work, "numerical solution" refers to using algorithms to find approximate answers to mathematical problems that can't be solved exactly. This often involves numerical methods for solving equations, optimizing functions, or approximating values.

Knuth emphasizes the importance of designing efficient algorithms, as well as understanding and managing errors that can arise in numerical computations. Since approximations can introduce inaccuracies, error analysis is crucial to assess the reliability of results.

Common techniques include iterative methods, where initial guesses are refined through repeated calculations until a satisfactory answer is achieved. Stability (ensuring small input changes don’t drastically affect output) and convergence (the approximation getting closer to the true solution with more iterations) are key considerations.

Overall, Knuth’s insights into numerical solutions have greatly impacted fields like engineering, physics, and computer science, where complex problems often require computational approaches for practical solutions.