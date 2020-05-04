The kmeans objective is:
$$
\sum_{x_i \in \Chi}\sum_{\mu_j \in \Mu}||x_i - \mu_j||^2\mathbb{I}(\mu_j = \arg\min_{\mu_k \in \Mu} ||x_i-\mu_k||^2)
$$
We replace the identity function with a "soft" function $G(x, \mu, \Mu, \alpha)$ that is differentiable and: 
$$
\lim_{\alpha \to \infty} G \to \mathbb{I}(\mu = \arg\min_{\mu_k \in \Mu} ||x-\mu_k||^2)
$$
One such function is the soft-min:
$$
G(x_i,\mu_j,\Mu,\alpha) = \frac{e^{-\alpha ||x_i - \mu_j||^2}}{\sum_{\mu_k \in \Mu} e^{-\alpha ||x_i - \mu_k||^2}}
$$
Combining soft k-means with autoencoder, we get a fully differentiable objective.



Regularized OT
$$
\min_{\theta} \inf_{\pi \in \Pi()} \sum_{i,j} \pi_{ij} M_{ij}(\theta) 
$$
