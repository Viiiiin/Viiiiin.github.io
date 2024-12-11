---
layout: default
title: Homework10
permalink: /homework10
---
To see the answer to the question of homework 10 [click on this link](hw10Theory.md)
![hw](../assets/img/hw10.png)
[GitHub](https://github.com/Viiiiin/Statistics/blob/main/homework_2/homework_1/hw10.cs)
# Numerical Integration with Riemann and Lebesgue Methods

This code implements a **numerical integration** framework in C# that calculates the integral of a function over a specified interval using two different methods:
- **Riemann Integration**
- **Lebesgue Integration (approximated)**

Additionally, the code includes a graphical visualization of the function and labels showing the results of the integrals.

## Components of the Code

### 1. **Constructor and Initialization**
The constructor initializes the parameters required for numerical integration:

### 2. **X-Values Generation**
The method `GenerateXValues` divides the interval `[lowerBound, upperBound]` into `intervals` equally spaced points, which are stored in a list. These points serve as evaluation nodes for the function.

### 3. **Riemann Integral Calculation**
The Riemann integral is computed using the **left Riemann sum**:

$$
\text{Integral}_{\text{Riemann}} = \sum_{i=0}^{n-1} f(x_i) \cdot \Delta x
$$

Here, \(\Delta x\) is the width of each subinterval.

### 4. **Lebesgue Integral Calculation**
The Lebesgue integral is approximated by grouping function values (\(y=f(x)\)) into buckets and associating a measure (sum of widths \(\Delta x\)) to each level. The formula used is:

$$
\text{Integral}_{\text{Lebesgue}} = \sum_{\text{buckets}} (\text{level} \times \text{measure})
$$

This is a simplified approach to illustrate the concept of **measure theory**, focusing on the codomain \(y\) rather than the domain \(x\).

### 5. **Graphical Representation**
The `DrawFunction` method uses the `Graphics` class to plot the function and its corresponding integration results:
- The **function curve** is drawn in red.
- A **grid** and labeled axes provide context for the visualization.
- Calculated values for Riemann and Lebesgue integrals are displayed on the graph using labels.

### 6. **Paint Method**
The `Paint` method hooks into the `PaintEventArgs` of a `Form` or `Panel` to render the graph and compute the integral values.

## Differences Between Riemann and Lebesgue Integrals

### Conceptual Difference
- **Riemann Integration**: Sums up the areas of vertical slices of the function (using the domain \(x\)). This method relies on the function being well-behaved over the interval (e.g., continuous).
- **Lebesgue Integration**: Groups the range (codomain \(y\)) into levels and measures the "size" of the domain corresponding to each level. This is more general and works for functions with discontinuities or on sets of measure zero.

### Numerical Difference
In practice:
- The **Riemann integral** may be more accurate for smooth, continuous functions.
- The **Lebesgue integral approximation** introduces rounding when grouping values into buckets, potentially leading to small numerical discrepancies.

### Output Example
For a function \(f(x) = x^2\) over \([0, 1]\) with 100 intervals:
- **Riemann Integral**: \(0.32835\)
- **Lebesgue Integral**: \(0.32790\) (slight difference due to bucketing and rounding)



# SSL/TLS Certificate Transparency Statistical Analysis

## Objective

Analyze publicly available SSL/TLS certificates to:
- Identify patterns and trends.
- Highlight potential security risks.
- Compare practices across domains/industries.

---

## 1. Data Collection

### **Sources of SSL/TLS Certificates**
- Certificate Transparency (CT) logs (e.g., using APIs like [crt.sh](https://crt.sh/) or Google’s CT log servers).
- Open-source tools for fetching and parsing certificates (e.g., `ctlogs`, `x509` modules in Python).

### **Sample Features to Extract**
For each certificate, extract the following:
- **Issuer**: The Certificate Authority (CA).
- **Validity Period**: Start and end dates.
- **Geographic Location**: From the subject or issuer fields.
- **Encryption Details**: Key length, signature algorithm, and cipher suite.
- **Domain Information**: Top-level domains (TLDs) and specific industries.

---

## 2. Feature Engineering

### **Transform Data for Analysis**
- Compute **validity durations** from start and end dates.
- Parse key lengths (e.g., RSA-2048, RSA-4096).
- Aggregate by TLDs (e.g., `.com`, `.org`) and industries (e.g., finance, healthcare).
- Group by certificate authorities (CAs).

---

## 3. Statistical Analysis

### **Key Metrics**
1. **Certificate Issuer Distribution**:
   - Count the number of certificates issued by each CA.
   - Identify the most common and least common CAs.

2. **Certificate Validity Durations**:
   - Calculate **mean**, **median**, and **variance** for validity durations.
   - Classify certificates as **short-lived** (< 1 year) or **long-lived** (> 1 year).

3. **Encryption Strength**:
   - Distribution of key lengths (e.g., RSA-2048 vs RSA-4096).
   - Proportion of outdated algorithms (e.g., SHA-1).

4. **Geographic Distribution**:
   - Number of certificates by country/region.
   - Identify regions with potential risks (e.g., self-signed certificates).

5. **Domain-Level Insights**:
   - Common practices in specific industries.
   - Analyze certificate policies across TLDs (e.g., `.edu` vs `.gov`).

---

## 4. Example Statistical Results

### (a) Certificate Issuer Distribution
| Issuer                | Count    | Proportion (%) |
|-----------------------|----------|----------------|
| Let's Encrypt         | 450,000  | 60.2%          |
| DigiCert              | 200,000  | 26.8%          |
| GlobalSign            | 50,000   | 6.7%           |
| Others                | 47,000   | 6.3%           |

### (b) Certificate Validity Periods
- **Mean Validity**: 398 days.
- **Median Validity**: 365 days.
- **Short-Lived Certificates (<90 days)**: 58%.
- **Long-Lived Certificates (>1 year)**: 10%.

### (c) Key Length Distribution
| Key Length   | Count    | Proportion (%) |
|--------------|----------|----------------|
| RSA-2048     | 700,000  | 93.3%          |
| RSA-4096     | 35,000   | 4.7%           |
| ECC-256      | 15,000   | 2.0%           |

### (d) Geographic Distribution
| Country      | Certificates Issued | Proportion (%) |
|--------------|----------------------|----------------|
| US           | 400,000             | 53.4%          |
| Germany      | 100,000             | 13.3%          |
| China        | 70,000              | 9.3%           |
| Others       | 180,000             | 24.0%          |

---

## 5. Potential Security Insights

1. **High Proportion of Short-Lived Certificates**:
   - Certificates with a validity of 90 days or less are increasing due to automation (e.g., Let's Encrypt).
   - Short validity improves security by reducing attack windows but might indicate trends in automation.

2. **Use of Outdated Algorithms**:
   - A small percentage (e.g., 2%) of certificates still use SHA-1, which is deprecated.
   - RSA-2048 dominates, but ECC adoption (e.g., ECC-256) is increasing.

3. **Regional Security Risks**:
   - Regions with high self-signed certificates or outdated CAs pose risks.
   - Concentration of certain issuers in specific regions may indicate monopolistic practices or compliance trends.

4. **Industry Trends**:
   - Government and finance sectors prefer long-lived certificates.
   - Educational institutions and tech industries rely more on automated short-lived certificates.

---
