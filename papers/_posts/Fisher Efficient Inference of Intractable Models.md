Fisher Efficient Inference of Intractable Models



MLE requires normalization term

Use Stein but avoids kernel

Use density ration estimation??



P: model

Q: data



forward KL, without latent => maximum likelihood

$\min KL(Q|P) = C - \max \mathbb{E}_{q}[\log p(x)]$



2 sample density ratio estimation

To estimate the ratio $r(x) = \frac{q(x)}{p(x,\theta)}$, estimate $\delta: r(x,\delta) = \frac{q(x;\delta)}{p(x)}$. The below optimization makes $q(x;\delta) \approx q(x)$:

$\min KL(Q|Q_{\delta}) = C - \mathbb{E}_q [\log r(x;\delta)]\quad s.t. \int r(x;\delta)p(x)dx = 1$



This is called KL Importance Estimation Procedure. Note that the constraint uses $p$, so we need samples from both $q$ and $p$ for optimization and constraint respectively.



Stein's identity: Let $\mathbb{E}_p[T_p(f)(x)] = 0$ and $r_{\theta}(x;\delta) = \delta^T T_{\theta}(f)(x) + 1$, then $\int_r(x;\delta)p(x)dx = 1$, so the constraint is automatically satisfied if we force $r$ to be parameterized this way. Also, $\log r_{\theta}(x;\delta)$ is concave w.r.t. $\delta$ so there is only 1 local optimum



$r_{\theta}(x;\delta) = \frac{q(x;\delta)}{p(x;\theta)}$

$KL(Q||P_{\theta}) = \mathbb{E}_q \frac{q(x;\delta)}{p(x;\theta)}$

Min-Max problem:
$$
\min_{\theta} KL(Q||P_{\theta}) = \min_{\theta}\max_{\delta} \mathbb{E}_{q}\frac{q(x;\delta)}{p(x;\theta)}
$$
Choosing $f$? In the paper they used a pre-trained DNN. basically an embedding map.