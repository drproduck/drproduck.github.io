Hierarchical Optimal Transport



###### Barycenter Computation

There are 2 main **styles** of computing barycenter depending on the type of data:

1. **fixed supports** (Eulerian): This is seen in CV application (the supports are pixel coordinates) and NLP (the supports are word embeddings). One can even restrict the solution this way (without interpretation). The advantage of this approach is we don't have to train the supports, and there is a fast Sinkhorn-like algorithm (<cite>[Benamou][1]</cite>)
2. **trainable supports ** (Lagrangian): Allows maximum flexibility, but is harder. Most papers alternate between minimizing w.r.t the mass and the supports [2]

Note that the barycenter loss is a sum:
$$
\min_a \sum_i \lambda_i W_2(a, b_i)
$$
a stochastic method that samples $b_i$ has been investigated in [2].



###### Wasserstein Dictionary Learning [4]

Given $\{x_i\}_{i=1}^n \in \mathbb{R}^{n \times d}$, Wasserstein dictionary learning learns a set of codes ${y}_{i=1}^m \in \mathbb{R}^{m \times d}$ and weights $\{w\}_{i=1}^n \in \mathbb{R}^{n \times m}$ that minimizes:
$$
\min_{Y, W} \sum_i \mathcal{L}\left(x_i, \arg \min_{a_i} \sum_j w_{ij} W_2(a_i, y_j) \right)
$$
Recall that the usual dictionary learning problem uses weighted sum in place of Wasserstein barycenter and non-negative weights instead of probabilities. Sparsity can be achieved in both case by adding $L_1$ loss on the weights.

WDL was used for topic modeling in [5]. In topic modeling, a document is posited as the mixture of topics. The generative process is:

1. pick a topic according to topic distribution (specific to each document)
2. pick a word according to word distribution of the chosen topic.

This is the core of Latent Dirichlet Allocation. It can be shown to be equivalent to a matrix factorization.



###### Wasserstein K-means

To cluster distributions (cloud points), we can use Wasserstein distances instead of Euclidean distances. [6]

**Note** that K-means is equivalent to the variational Wasserstein problem: 
$$
W_2 (G, P)
$$


Recently there have been some papers that used OT on OT: An OT-based distance is used as the ground metrics.  We first investigate the common components in these models.

Hierarchical OT

Multilevel Clustering

Hierarchical OT for Multimodal Distribution Alignment





[1]: Iterative Bregman projections for regularized transportation problems.

[2]: Fast computation of Wasserstein Barycenters.

[3]: Stochastic Wasserstein Barycenters.

[4]: Wasserstein dictionary learning: Optimal transport-based unsupervised nonlinear dictionary learning

[5]: Distilled wasserstein learning for word embedding and topic modeling

[6]: Wasserstein k-means++ for cloud regime histogram clustering