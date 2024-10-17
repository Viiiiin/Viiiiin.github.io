---
layout: default
title: Homework2Theory
permalink: /hwTheory2.html
---


# Welford's Recursion Derivation

The following steps illustrate the derivation of Welford's recursion for calculating variance:
$$
(N - 1)s^2_N - (N - 2)s^2_{N-1} = \sum_{i=1}^{N}(x_i - \bar{x}_N)^2
$$

$$
= \sum_{i=1}^{N-1}(x_i - \bar{x}_{N-1})^2 + (x_N - \bar{x}_N)^2
$$

$$
= (x_N - \bar{x}_N)^2 + \sum_{i=1}^{N-1}\left((x_i - \bar{x}_{N-1})^2 - (x_i - \bar{x}_N)^2\right)
$$

$$
= (x_N - \bar{x}_N)^2 + \sum_{i=1}^{N-1}(x_i - \bar{x}_{N-1})(x_i - \bar{x}_N)
$$

$$
= (x_N - \bar{x}_N)^2 + (x_N - \bar{x}_{N})(\sum_{i=1}^{N-1}(x_i - \bar{x}_{N-1}))
$$

$$
= (x_N - \bar{x}_N)(x_N - \bar{x}_{N-1})
$$

