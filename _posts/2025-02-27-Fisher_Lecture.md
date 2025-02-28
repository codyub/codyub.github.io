---
layout: single
title: "Fisher Lecture: Dimension Reduction in Regression(Review)"
categories: Study
tag: [paper, thesis]
toc: true
author_profile: false
sidebar:
    nav: "docs"
---

Introduction
===
- principal components are computed from the marginal distribution of X and consequently the leading components may have little necessary relation with the response.
- marginal of X would necessarily be structured so that the leading principal components contain the essential information about the response. 
- In this paper, we concentrate on X|Y, although the goal is to reduce the dimension reduction of X with little or no loss of information on Y|X.
- To read this paper, basic understanding of the concept of sufficient dimension reduction might be needed. 

Notation
---
- subspaces: $\mathcal{S}(\centerdot)$


Principal Component model (PC regressionn model)
===
consider the multivariate model for the inverse regression: 
$$X_y = \mu + \Gamma\nu_y +\sigma\epsilon$$

- under the inverse model above, the distribution Y|X is the same as the distribution of $Y|\Gamma^TX$ for all values of X
- X can be replaced by the sufficient reduction $\Gamma^TX$ without loss of information on the regression Y on X.
- this model indicates that the conditional means fall in the d-dimensional subspace $\mathcal{S}\_\Gamma$ and the columns of $\Gamma$ span $\mathcal{S}_{Y|X}$.
- $\Gamma$ and $\nu_y$ are not simultaneously estimable, However, the reductive subspace $\mathcal{S}\_\Gamma = span(\Gamma)$ is estimable.
- $\Gamma$ is estimated by maximizing the likelihood function of $X_y$
- As a result, maximum likelihood estimator $\hat{\mathcal{S}\_\Gamma}$ of $\mathcal{S}\_\Gamma$ is $span({\hat{\gamma_1},...,\hat{\gamma_d}})$, which are eigenvectors of $\hat{\Sigma}$.
- That is, Using PCA from scratch could be working.

Notation
---
- $\mu \in \mathbb{R}^p$
- $\Gamma \in \mathbb{R}^{p\times d} (d < p)$, d is assumed to be known
- $\Gamma^T\Gamma = I_d$
- $\sigma \ge 0 $
- $\nu_y \in \mathbb{R}^d$ : coordinate vector(unknown function of y that have a positive definite sample covariance matrix)
- $\epsilon \in \mathbb{R}^p$ (to be independent of Y), ~ $N(0,\Sigma)$


Principal Fitted Component model(isotonic)
===
PC regression model does not use observed response and does not hold potential response.
By modeling $nu_y$, we can adapt the reduction for a specific response. 
$$X_y = \mu + \Gamma\beta f_y +\sigma\epsilon$$
- $\Gamma^T X$ is still a sufficient reduction. 


Notation
---
- $nu_y = \beta f_y$, where $\beta \in \mathbb{R}^{d\times r}, d\le r$
- $f_y$ is known vector-valued function of the response with $\Sigma_y f_y = 0$
- $\Sigma_{fit}$
- $\Sigma = \Sigma_{fit} + \Sigma_{res}$

Example code
---



Principal Fitted Component model(structured)
===



Principal Fitted Component model(unstructured)
===



