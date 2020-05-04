Wasserstein Autoencoder 

![1570714898140](/home/khiem/.config/Typora/typora-user-images/1570714898140.png)

So, finding the optimal coupling equals to finding the optimal encoder. Note "deterministic"

![1570767661465](/home/khiem/.config/Typora/typora-user-images/1570767661465.png)

D_Z has been either GAN (which reduces to AVB) or MMD (the German's)



Adversarial Variational Bayes

![1570763570975](/home/khiem/.config/Typora/typora-user-images/1570763570975.png)

Replace the KL(q(z|x), p(z)) with GAN objective, so that the optimal solution is $\log q(z|x) - \log p(z)$. See [3] for proof. $Q_e$ is basically a conditional GAN with input X and noise $\epsilon$



Adversarial Autoencoder.

Introducing the aggregate posterior $p(z) = \int p(z|x)p(x) dx$

![1570765453624](/home/khiem/.config/Typora/typora-user-images/1570765453624.png)

![1570765511223](/home/khiem/.config/Typora/typora-user-images/1570765511223.png)

First phase train the autoencoder reconstruction loss. Second phase, sample some latent codes (negative) and some Gaussian vectors (positive) and train GAN to distinguish.

[2] Adversarial autoencoder

[3] Adversarial Variational Bayes

