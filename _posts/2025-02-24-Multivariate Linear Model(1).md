---
layout: single
title: "Multivariate Linear Model and Response Envelope"
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
Background
---
- analyzing data with high dimensional y(response variable) and relatively low dimensional X(predictor) is often difficult
- Thus, low dimensional linear transform of Y that describes the regression relationship would be helpful.
- Most of dimension reduction methods have focused on reducing the dimension of X.

Envelope
---
- the smallest subspace $\mathcal{E}$ of $\mathbb{R}^r$ with the properties that, for all relevant $\mathbb{x1}$ and $\mathbb{x2}$.
```math
\mathbb{Q}_\mathcal{E} \mathcal{Y}|(\mathcal{X}=\mathcal{x1})\sim \mathbb{Q}_\mathcal{E} \mathcal{Y}|(\mathcal{X}=\mathcal{x2})
```
```math
\mathbb{P}_\mathcal{E} \mathcal{Y} \perp \mathbb{Q}_\mathcal{E} \mathcal{Y}|\mathcal{X}
```


- $\mathbb{P}_{\mathcal{E}}$: projection onto $\mathcal{E}$.
- $\mathbb{Q}_{\mathcal{E}} = \mathbb{I}\_{\mathcal{r}} - \mathbb{P}\_{\mathcal{E}}$
- by intoducing the concept of envelope, low dimensional linear transform of Y become possible.

- 어떻게 가능해지는지 이론 추가 필요!

Example
---
- $Y = \alpha + \beta X + \varepsilon$
- $Y = (Y_1,Y_2)^T$ a multivariate regression with r = 2
- $X \in {0,1}$ a single binary predictor
- $\varepsilon\sim\mathcal{N}(0,\Sigma)$
goal: How are the values of Y different when X is 0 and 1?

general approach 
---
- Explore the distribution of Y in both cases(X=0, X=1)
- weakness: projecting many points produces densities -> these densities could overlap, which means that it may take a large sample size to infer $\beta$ and it is difficult to analyze the effect of X

Envelope method
---
- Envelope method finds meaningful direction by using eigenvector of \Sigma
- In this paper, Envelope Subspace aligns with Principal Component, which means that the distribution would be clearly identified if we transform data based on important directions.
- When the data is converted in the direction of Envelope Subspace (in this paper: diagonal), the two groups are clearly separated.
- 결과적으로, Envelope 분석을 하면 회귀 분석에서 중요한 차원만 남기고, 불필요한 변동을 제거할 수 있음! = efficiency gain from an envelop analysis 


Reference
---
R. Dennis Cook(2018) Principal Components, Sufficient Dimension Reduction, and Envelopes



