Notes on Deep Clustering

lambda ($\lambda$): weight of cluster loss (composite distance)

eta ($\eta$): weight of cluster weight entropy

Before

![76661224_578780582665859_5755177939515736064_n](/home/khiem/Downloads/76661224_578780582665859_5755177939515736064_n.png)

12/20

entropic cluster weight
$$
\mathcal{L}_{ae} + \lambda D(Q_Z,P_Z) - \eta H(C)
$$
where $C = D^T1$ for $D_{ij} = D(Q(Z|X_i), P(Z|\theta_j))$

entropic_mnist_latent=16_lambda=20.0_eta=1.000, loss=L2sq. The covariance matrix was clipped below at 0.1. Acc = 96.34

![entropic_mnist_latent=16_lambda=20.0_eta=1.000](/home/khiem/Downloads/entropic_mnist_latent=16_lambda=20.0_eta=1.000.png)

Without clipping, but covariance started at 1.0. Acc = 88.4

![entropic_mnist_latent=16_lambda=20.0_eta=1.000_relaxed](/home/khiem/Downloads/entropic_mnist_latent=16_lambda=20.0_eta=1.000_relaxed.png)



loss=bernoulli, lambda = 20, acc = 86.97

![entropic_mnist_bernoulli_latent=16_lambda=20.0_eta=1.000](/home/khiem/Downloads/entropic_mnist_bernoulli_latent=16_lambda=20.0_eta=1.000.png)

lambda = 100, acc = 98.4 (Was this a fluke???)

![entropic_mnist_bernoulli_size=32_latent=16_lambda=100.0_eta=1.000](/home/khiem/Downloads/entropic_mnist_bernoulli_size=32_latent=16_lambda=100.0_eta=1.000.png)

With latent_dim = 128, loss=L2sq, acc=86.5

![entropic_mnist_latent=128_latent=16_lambda=20.0_eta=1.000](/home/khiem/Downloads/entropic_mnist_latent=128_latent=16_lambda=20.0_eta=1.000.png)