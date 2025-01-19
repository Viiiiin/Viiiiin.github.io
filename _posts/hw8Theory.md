---
layout: default
title: Homework8Theory
permalink: /hwTheory8.html
---

# Shannon Entropy and Diversity Measures

## Shannon Entropy
Shannon entropy is a measure of uncertainty or randomness in a distribution. It is defined as:
$$
H(X) = - \sum_{i} p_i \log p_i
$$
where:
- \( p_i \): Probability of the \(i\)-th outcome.
- \( H(X) \): Entropy of the random variable \(X\).

### Properties of Entropy:
1. \( H(X) \geq 0 \): Entropy is always non-negative.
2. For a uniform distribution, entropy is maximized: 
   $$ H(X) = \log n $$ 
   where \(n\) is the number of possible outcomes.

### Other Diversity Measures:
1. **Gini-Simpson Index**:
   $$ 
   D = 1 - \sum_{i} p_i^2
   $$
   Measures the probability that two randomly selected outcomes are different.
   
2. **Renyi Entropy**:
   $$ 
   H_\alpha(X) = \frac{1}{1 - \alpha} \log \left( \sum_{i} p_i^\alpha \right)
   $$
   where \(\alpha > 0\) and \(\alpha \neq 1\).

3. **Tsallis Entropy**:
   $$ 
   S_q(X) = \frac{1}{q - 1} \left( 1 - \sum_{i} p_i^q \right)
   $$
   where \(q > 0\) and \(q \neq 1\).

---

## Primitive Roots

### Definition
A **primitive root modulo \(p\)** (a prime number) is an integer \(g\) such that for every integer \(a\) coprime to \(p\), there exists an integer \(k\) satisfying:
$$
g^k \equiv a \pmod{p}
$$
This means \(g\) generates all the integers coprime to \(p\) under modular exponentiation.

### Properties:
1. If \(g\) is a primitive root modulo \(p\), then the powers \(g^1, g^2, \dots, g^{\phi(p)}\) (where \(\phi(p) = p-1\)) are distinct modulo \(p\).
2. The number of primitive roots modulo \(p\) is \(\phi(\phi(p))\), where \(\phi\) is the Euler totient function.

### Example:
For \(p = 7\), \(g = 3\) is a primitive root because:
\[
3^1 \equiv 3 \pmod{7}, \quad 3^2 \equiv 2 \pmod{7}, \quad 3^3 \equiv 6 \pmod{7}, \quad \text{etc.}
\]
The set generated is \(\{1, 2, 3, 4, 5, 6\}\), covering all integers coprime to \(7\).

### Formula for Powers:
The \(k\)-th power of \(g\) modulo \(p\) is:
$$
g^k \mod p = (g \cdot g \cdot \dots \cdot g) \mod p \quad \text{(with \(k\) multiplications)}.
$$

### Practical Use:
Primitive roots are fundamental in number theory and are used in cryptographic algorithms like Diffie-Hellman key exchange.

---

