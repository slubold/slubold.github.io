---
layout: default
---

## LS Geometry Summary

[ArXiv version](https://arxiv.org/abs/2012.10559). Last updated: Feb 16, 2021. 



This note provides a short summary of the paper "Identifying the latent space geometry of network models through analysis of curvature." 

# Introduction 
The latent space (LS) model, originally proposed in Hoff (2002), uses low-dimensional representations of nodes to depict complex, high-dimensional dependencies between nodes in a network. We consider the following generative model.

$$P(g_{ij} = 1 | \nu, z)  = \exp(\nu_i + \nu_j - d_{\mathcal{M}}(z_i, z_j))$$
 
 where $$\{\nu_i\}$$ are the node-specific propensity to form edges, $$\{z_i\}$$ are the latent space locations of the nodes, and $$d_{\mathcal{M}^p(\kappa)}(z_i, z_j)$$ is the distance along the surface of $$\mathcal{M}^p(\kappa)$$. Our goal is to answer: "Given $$g$$ drawn from the LS model, can we estimate the geometry type, dimension, and curvature of $$\mathcal{M}^p(\kappa)$$?
 
 # Embedding Approach
 
 To motivate our approach, we consider a related problem. Suppose we observe a $$K \times K$$ matrix $$D$$ that contains the pairwise distances between $$K$$ unknown points on $$\mathbb{R}^2$$. For example, set $$K = 3$$ and let $$D$$ take the form
 
 $$D = \begin{pmatrix} 0 & 1 & 2 \\
 1 & 0 & \sqrt{3} \\
 2 & \sqrt{3} & 0
 \end{pmatrix} \;. $$
 
 
 These distances correspond to the three points plotted below at (0, 0), (1, 0), and (0, 2). Without the values of the points, can we determine just from $$D$$ that the three points used to compute $$D$$ are actually points in \emph{some} Euclidean space. The following result from Schoenberg (1935) tells us how to determine this.
 
 <b>Theorem (Schoenber 1935) </b> Let $$D$$ be a distance matrix betweek $$K$$ points $$\{z_1, \dotsc, z_K\}$$. Then $$Z$$ can be isometrically embedded in $$\mathbb{R}^{p}$$ for some $$p$$ if and only if 
 
 $$F(D) := -\frac 1 2 J D \circ D J $$
 
 is positive semi definite, where $$J$$ is the $$K \times K$$ [centering matrix](https://en.wikipedia.org/wiki/Centering_matrix) and $\circ$ is the Hadamard product.
 
 In our example $$D$$, the smallest eigenvalue of $$F(D)$$ is 0, which is consistent with the theorem above because the points are in $$\mathbb{R}^2$$.
 
