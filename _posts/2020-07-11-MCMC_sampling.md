---
title: Monte Carlo Markov Chain
date: {}
permalink: /posts/2020/07/MCMC_samping
tags:
  - Sampling
published: true
---
$$\documentclass{article}
\usepackage{amsmath}$$
MCMC Sampling is primarily used to sample from a complicated probability density function $p(x)$ or to approximate an expectation of a function $E[f(x)]$ where $x \sim p(x)$.

To understand why this works well we need to understand some of the properties of a markov chain.

1. Time Homogenous
  - A Markov Chain is said to be homogenous if  $$P(X_{i + 1} = b | X_{i} = a) = T_{ab}$$ $\forall$ $i$ $\forall$ a, b $\in$ $\mathscr{X}$ for some matrix T. To put it simply it means that the transition from a to b will not depend at what time (or i) it is occuring.

  - For a discrete steps markov chain, the transition matrix is a stochastic matrix, which means that all entries are non-negative probabilites where rows sum up to 1. If it is a continuous space markov chain T will be replaced with a kernel, 
  $$\[ K : \mathscr{X} \to \mathscr{X} \]$$

2. Stationary Distribution
A pmf $\pi$ on $\mathscr{X}$ is a stationary distribution if $$\pi T =\pi$$ i.e. $$\sum_{a|in\mathscr{X})\pi_{a}T_{ab} = T_{ab}$$

3. Irreducible 
A markov chain($X_{i}$) is irreducible if $\forall$ a, b $\in$ $\mathscr{X}$ $\exists$ t $\geq$ 0 s.t. P($X_{t}$ = b | $X_{0}$ = a) > 0. This means that no matter where we start from, we will get to another point with probability p > 0.

4. Aperiodic Markov Chain 
An irreducible matrix M.C {$X_{i}$}, if $\forall$ a $\in$ $\mathscr{X}$,
$$ \[ \text{gcd} \text{{ t} : P(x_{t} = a | x_{0) = a) > 0} = 1 \] $$

5. Reversibility 
This is used in MCMC to construct a markov chain with a particular stationary distribution.

6. Ergodic Theorem 
  If $(X_{0}, X_{1}.... X_{n})$ is an irreducible time homogenous discrete MC with stationary distribution $\pi$, then 
  $$ \dfrac{1}{n} \sum_{i = 1}^{n) f(x_{i}) n\to\infty E[f(x)] $$  for any bounded function $f : \mathscr{X}\to\mathbb{R}$

  If further, it is aperiodic, then 
  $P(X_{n} = x | X_{0} = x_{0}) \to \pi(x) $ as $ n\to\infty$ $$\forall x, x_{0} \in \mathscr{X}$$
  We can start from anywhere and keep drawing from $P(X_{n} | X_{0})$ our distribution converges to the original stationary distribution(\pi(x))
