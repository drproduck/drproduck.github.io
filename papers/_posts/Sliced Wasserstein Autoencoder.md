Sliced Wasserstein Autoencoder

"This approach has two major limitations: 1) The KL-Divergence and in general f-divergences do
not provide meaningful dissimilarity measures for distributions supported on **non-overlapping lowdimensional manifolds** Arjovsky et al. (2017); Kolouri et al. (2018) (see supplementary material),
which is common in hidden layers of neural networks, and therefore they do not provide informative gradients for training φ, and 2) we are limited to distributions qZ that have **known explicit formulations**, which is restrictive as it eliminates the ability to use the much broader class of samplable distributions."

The optimization problem is:

![1570778901389](/home/khiem/.config/Typora/typora-user-images/1570778901389.png)

where the first is not wasserstein, but only a norm between the true X and generated $Y = \psi (\phi (X))$. The second term is:

<img src="/home/khiem/.config/Typora/typora-user-images/1570779031891.png" alt="1570779031891"  />

which is the sliced Wasserstein distance between samples $z$ from a predefined distribution (e.g. N(0, I)) and the latent code of the data X. Note M is batch size and L is number of projections.

Note: Glivenko-Cantelli Theorem: Empirical distribution converges almost surely

Note: How good is the empirical distribution wasserstein distance estimate? Here we have a bound for difference between W empirical (using M samples) and W

<img src="/home/khiem/.config/Typora/typora-user-images/1570780028218.png" alt="1570780028218"  />

Note: How good is sliced wasserstein? It is a true metric and a lower bound of wasserstein.

![1570781207344](/home/khiem/.config/Typora/typora-user-images/1570781207344.png)

![1570781277834](/home/khiem/.config/Typora/typora-user-images/1570781277834.png)

the second equation is when p=2 (L2-norm). note that d is the dimension.



Generative Modeling using the Sliced Wasserstein Distance (CVPR)

When computing Wasserstein distance between 2 sets of data points.

![1570775692604](/home/khiem/.config/Typora/typora-user-images/1570775692604.png)

Which requires finding a doubly-stochastic matrix with integral entries (i.e. permutation matrix)

<img src="/home/khiem/.config/Typora/typora-user-images/1570776079542.png" alt="1570776079542"  />

Note: this paper matches distributions in data space

Note: They use an intermediate embedding in the network as "projection" first. The W distance between these projections are then compared. The argument made is these learned embedding (eq 2) support slicing (eq 1). Linear discriminant analysis is mentioned.

<img src="/home/khiem/.config/Typora/typora-user-images/1570777530902.png" alt="1570777530902"  />

