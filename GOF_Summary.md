---
layout: default
---

# Network GoF Summary

This note is intended to briefly explain the main idea of .  

# Is there code?

Yes, check out the github repo [here](https://github.com/slubold/Network_GOF). 


Let $$G$$ denote a random network that is either completely observed (meaning we observe all nodes and edges) or partially observed (from, for example, Aggregated Relatonal data). Suppose our goal is to determine if a given parameteric network model, such as a stochastic block model, fits the observed network well. We call this the goodness of fit (GoF) hypothesis. In this work, we derive a hypothesis testing framework to test this hypothesis in both the completely observed and partially observed cases.

The main approach, which was explored in Jing (2016) and others, is that the smallest and largest eigenvalues of the $$n \times n$$ random matrix $A$, whose entries are independent, have mean zero and variance $1/(n-1)$, converge in distribution to the Tracy-Widom distribution.  To apply this to the network GoF problem, suppose that we have a random network $$G$$ drawn from a distribution $$F_\theta$$. Suppose we compute an estimate $$\hat \theta$$ of $$\theta$$ using, for example, maximum likelihood estimation. We can then estimate $$P(G_{ij} = 1 \mid \hat \theta)$$ using the parametric form of the model.

We then form the symmetric random matrix $$\hat A$$, with $$\hat A_{ii} = 0$$ and for $$i \neq j$$,

$$ \hat A_{ij} = \frac{G_{ij} - \hat P_{ij}}{\sqrt{(n-1)\hat P_{ij}(1-\hat P_{ij})}}.  $$

By construction, $$\hat A$$ is a symmetric random matrix whose entries are (approximately) independent, have mean zero, and variance $$1/(n-1)$$, so $$\lambda_{\min}(\hat A)$$ and $$\lambda_{\max}(\hat A)$$ both converge to a Tracy-Widom distribution. This allows us to construct a test statistic based on the eigenvalues of $$\hat A$$ to test the GoF hypothesis. 

# Directed and partially observed cases
The above discussion only applies to un-directed networks, which have symmetric adjacency matrices. We extend this method to the case of directed networks by using a result from Chafai that shows that the largest singular values of a non-symmetric matrix $$A$$, that takes a form that is similar to the form of $$\hat A$$, converges to a Tracy-Widom distribution. This allows us to create a test of the GoF hypothesis when $$G$$ is directed. We also show how to use this result to test the GoF hypothesis when we only observe partial network data, such as Aggregated Relational data. 









