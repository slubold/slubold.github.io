---
layout: default
---

## Network GoF Summary

This note is intended to briefly explain the main idea of .   

The main approach, which was explored in Jing (2016) and others, is that the eigenvalues of the $$n \times n$$ random matrix $A$, whose entries are independent, have mean zero and variance $1/n$, converge in distribution to the Tracy-Widom distribution. 

To apply this to the network GoF problem, suppose that we have a random network $$G$$ drawn from a distribution $$F_\theta$$. Suppose we compute an estimate $$\hat \theta$ of $$\theta$$ using, for example, maximum likelihood estimation. We can then estimate $$P(G_{ij} = 1 | \hat \theta)$$. We then form the random matrix 

$$ \hat A_{ij} = \frac{G_{ij} - \hat P_{ij}}{\sqrt{(n-1)\hat P_{ij}(1-\hat P_{ij})} $$







