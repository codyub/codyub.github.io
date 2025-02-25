---
layout: single
title: "Multivariate Linear Model and Response Envelope(1)"
categories: Study
tag: [paper, thesis]
toc: true
author_profile: false
sidebar:
    nav: "docs"
---


Multivariate Linear Model
===

- $Y \in \mathbb{R}^r , X \in \mathbb{R}^p , \alpha \in \mathbb{R}^r (vector of intercepts), \beta \in \mathbb{R}^{r\times p},  \bar{X} = 0, \varepsilon\sim\mathcal{N}(0,\Sigma)$
- $Y = \alpha + \beta X + \varepsilon$

ordinary least squares estimator of $\beta$ can be contructed by doing $\mathbb{r}$ seperate univariate linear regressions. If some elements of $\beta$ are linked over rows, then closed form expression for the MLE of $\beta$ and $\Sigma$ may not be possible.

Response Envelopes
===

- the smallest subspace $\mathcal{E}$ of $\mathbb{R}^r$ with the properties that, for all relevant $\mathbb{x1}$ and $\mathbb{x2}$.
```math
\mathbb{Q}_\mathcal{E} \mathcal{Y}|(\mathcal{X}=\mathcal{x1})\sim \mathbb{Q}_\mathcal{E} \mathcal{Y}|(\mathcal{X}=\mathcal{x2})
```
```math
\mathbb{P}_\mathcal{E} \mathcal{Y} \perp \mathbb{Q}_\mathcal{E} \mathcal{Y}|\mathcal{X}
```


- $\mathbb{P}_{\mathcal{E}}$: projection onto $\mathcal{E}$.
- $\mathbb{Q}_{\mathcal{E}} = \mathbb{I}\_{\mathcal{r}} - \mathbb{P}\_{\mathcal{E}}$






