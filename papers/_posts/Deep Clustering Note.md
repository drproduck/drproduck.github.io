Constraint Optimization + Random Encoder



We train in 2 stages:

1) Pretrain the autoencoder, without any prior constraint. Let the moving average (taken in the last epoch) of the reconstruction loss be $\mathcal{L}_{AE}^{pre}$

2) Constraint Optimization using Method of Multipliers:
$$
\min_{\mathcal{L}_{AE} \le \mathcal{L}_{AE}^{pre}} D(q(z), p(z))
$$

![image-20191209174517000](/home/khiem/.config/Typora/typora-user-images/image-20191209174517000.png)

![image-20191209174604856](/home/khiem/.config/Typora/typora-user-images/image-20191209174604856.png)





Updates

Constraint Optimization doesnt work well

Fixing mu, lamba is now less sensitive

Fixing per-data variance

Trouble with activation function: consistently high accuracy, but can't generate images



Mutual information perspective?

Maximize mutual information I(X, Z), Z is often class one hot vector

Augment trick: Augment data, force embedding to be similar



Hand-design a prior???

