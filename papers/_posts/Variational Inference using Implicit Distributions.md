Variational Inference using Implicit Distributions

Note: the focus of this paper is on inference, not learning, so there is no learning $\theta$

Note: A potentially useful identity:

![1570865963767](/home/khiem/.config/Typora/typora-user-images/1570865963767.png)

Hint: Decompose $\log \frac{q_{\psi}(z)}{p(z)} = \log \frac{q_{\psi}(z)}{q_{\psi_0}(z)} + \log \frac{q_{\psi_0(z)}}{p(z)}$

Using this, we actually then have to use log derivative.



Here, the prior contrastive term $r(z,x_n) = \log \frac{q(z|x_n)}{p(z)}$ emphasizes the mismatch between approximate posterior and prior. 

![1570855360033](/home/khiem/.config/Typora/typora-user-images/1570855360033.png)

The joint contrastive term $s(z,x_n) = \log \frac{q(z|x_n)q(x)}{p(z,x_n)}$ emphasizes the mismatch between the joints. The leftover term is the entropy of true data. Note this could be divided by $N$.

![1570855468671](/home/khiem/.config/Typora/typora-user-images/1570855468671.png)

Note: minimizing $KL(q_{\psi}(z,x)||p_{\theta}(z,x))$ equals maximizing $ELBO$, which is a corollary of the above.

The adversarial method draws samples from 2 distributions and train a logistic regression classifier to discriminate them (note this is for $r(z,x_n)$)

![1570857073486](/home/khiem/.config/Typora/typora-user-images/1570857073486.png)

Note: this objective is not the log-ratio itself. When this classifier is close to a Bayes-optimum, then the log-ratio can be estimated. 

Note: joint contrastive examples are ALI and BiGAN, prior contrastive examples are Adversarial Variational Bayes

GAN-based method: there are 2 loops: inner loop learns the classifier, outer loop learns the inference network.

Denoising-based method:

Let $\tilde{x} = x + \epsilon, \epsilon \sim N(0,\sigma^2)$. Let $g$ (denoising function) be s.t. $g = argmin \mathbb{E}_{p(x,\tilde{x})}||g(\tilde{x}) - x||^2$. The following allows one to compute gradient  $\nabla_x \log p(x)$  [1]

![1570864301509](/home/khiem/.config/Typora/typora-user-images/1570864301509.png)

For $\nabla_z \log q(z|x)$:

![1570864616868](/home/khiem/.config/Typora/typora-user-images/1570864616868.png)

Using denoising objective, the gradient of ELBO is:

![1570864738294](/home/khiem/.config/Typora/typora-user-images/1570864738294.png)



[1] http://www.aihelsinki.com/connection-to-g/

