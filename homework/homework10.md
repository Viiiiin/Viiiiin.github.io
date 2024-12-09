---
layout: default
title: Homework10
permalink: /homework10
---
To see the answer to the question of homework 10 [click on this link](hw10Theory.md)

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

## 6. Tools and Methods

### **Data Collection**
- Use APIs like `crt.sh`, `x509` libraries, or custom scrapers for CT logs.

### **Statistical Analysis**
- Python libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`.
- Compute metrics (e.g., mean, median, variance) and generate plots.

### **Visualization**
- Histograms for validity durations.
- Pie charts for issuer distribution.
- Heatmaps for geographic distributions.

---

## 7. Recommendations

1. **Encourage ECC Adoption**:
   - Promote faster and more secure key exchange algorithms like ECC-256.
2. **Reduce Long-Lived Certificates**:
   - Transition to shorter-lived certificates for better security and automation.
3. **Address Regional Risks**:
   - Investigate and mitigate high concentrations of self-signed or weakly signed certificates in specific regions.

---