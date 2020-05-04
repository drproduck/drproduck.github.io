some monte-carlo estimator definitions

$$VAE_M(f, g) = \frac{1}{M} \sum_i \log \frac{g(x_i)}{f(x_i)},\quad x_i\sim f(x)$$

$IWAE_K(f,g) = \log \left(\frac{1}{K} \sum_i\frac{g(x_i)}{f(x_i)}\right), x_i \sim f(x)$



![graph](/home/khiem/Downloads/graph.png)



first estimator: $VAE\left(q(z|x), IWAE(q(v|x,y,z),p(x,y,z,v))\right)$

problem: the bound is less tight. 



second estimator: $VAE(q(z|x)l(z;y),IWAE(q(v|x,y,z), p(x,y,z,v)))$

problem: $q(z|x,y) \approx q(z|x)l(z;y)$ is a Gaussian. This regularization will influence $q(z|x)$



