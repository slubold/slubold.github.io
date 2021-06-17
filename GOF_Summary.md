---
layout: default
---

## Network GoF Summary

This note is intended to briefly explain the main idea of .   
Let $$G$$ denote a random network that is either completely observed (meaning we observe all nodes and edges) or partially observed (from, for example, Aggregated Relatonal data). Suppose our goal is to determine if a given parameteric network model, such as a stochastic block model, fits the observed network well. We call this the goodness of fit (GoF) hypothesis. In this work, we derive a hypothesis testing framework to test this hypothesis in both the completely observed and partially observed cases.

The main approach, which was explored in Jing (2016) and others, is that the smallest and largest eigenvalues of the $$n \times n$$ random matrix $A$, whose entries are independent, have mean zero and variance $1/(n-1)$, converge in distribution to the Tracy-Widom distribution.  To apply this to the network GoF problem, suppose that we have a random network $$G$$ drawn from a distribution $$F_\theta$$. Suppose we compute an estimate $$\hat \theta$$ of $$\theta$$ using, for example, maximum likelihood estimation. We can then estimate $$P(G_{ij} = 1 \mid \hat \theta)$$ using the parametric form of the model.

We then form the symmetric random matrix $$\hat A$$, with $$\hat A_{ii} = 0$$ and for $$i \neq j$$,

$$ \hat A_{ij} = \frac{G_{ij} - \hat P_{ij}}{\sqrt{(n-1)\hat P_{ij}(1-\hat P_{ij})}} .$$

By construction, $$\hat A$$ is a symmetric random matrix whose entries are (approximately) independent, have mean zero, and variance $$1/(n-1)$$, so $$\lambda_{\min}(\hat A)$$ and $$\lambda_{\max}(\hat A)$$ both converge to a Tracy-Widom distribution. This allows us to construct a test statistic based on the eigenvalues of $$\hat A$$ to test the GoF hypothesis. 









