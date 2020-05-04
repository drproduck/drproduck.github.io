Reweighted wake-sleep:

Use importance sampling to estimate gradient of both generative p and inference q

Wake phase for p:

$\nabla{\log p(x)} = \int p(z|x) \nabla \log p(x,z)$ (good to remember)

$= \int q(z|x)\frac{p(z|x)}{q(z|x)}\nabla \log p(x,z)$

$\approx \sum_i \tilde{w}_i \nabla \log p(x,z_i)$ where $w_i = \frac{p(x,z)}{q(z|x)}$ and $\tilde{w}_i = \frac{w_i}{\sum_j w_j}$

Update for q is similar (note we interpret the problem as minimizing the forward KL divergence $KL(p(z|x)|q(z|x))$:

Sleep phase = sampling z from prior. This requires then sampling x from p(x|z)

Wake phase = sampling x from data, then sampling z from posterior q(z|x), and use importance sampling. The gradient is:

$\sum_i \tilde{w}_i \nabla \log q(z_i|x) $

Note: forward Kl encourages mean-seeking behavior, while reverse Kl encourages mode-seeking behavior. Good importance sampling proposal requires mean-seeking behavior, thus forward Kl is better [1]



[1] Revisiting Reweighted Wake-Sleep for Models with Stochastic Control Flow

[2] Reweighted Wake Sleep

