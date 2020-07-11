---
title:  "Monte Carlo Markov Chain"
date: 2020-07-11
permalink: /posts/2020/07/MCMC_samping
tags:
  - Sampling 
---

An Introduction to Monto Carlo Markov Chain,

MCMC Sampling is primarily used to sample from a complicated probability density function $p(x)$ or to approximate an expectation of a function $E[f(x)]$ where $x \~{p(x)}$. To understand why this works well we need to understand some of the properties of a markov chain.

#### Some Properties of Markov Chain 

1. Ergodic Theorem : 

a) If $(X_{0}, X_{1}.... X_{n})$ is an irreducible time homogenous discrete MC with stationary distribution $\pi$, then 
$$ \frac{1}{n} \sum_{i = 1}^{n) f(x_{i}) n\to\infty E[f(x)]$$  for any bounded function $f : \mathscr{X}\to\mathbb{R}

b) If further, it is aperiodic, then <br>
$P(X_{n} = x | X_{0} = x_{0}) \to \pi(x) $ as $ n\to\infty$ $$\forall x, x_{0} \in \mathscr{X}$$
We can start from anywhere and keep drawing from $P(X_{n} | X_{0})$ our distribution converges to the original stationary distribution(\pi(x))

2. Time Homogenous
The formal definition is : A Markov Chain is said to be homogenous if  $P(X_{i + 1} = b | X_{i} = a) = T_{ab} \forall i \forall a, b \in \mathscr{X}$ for some matrix T. 






