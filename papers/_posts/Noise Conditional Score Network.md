Noise Conditional Score Network

Score Matching equals Fisher Divergence up to constant:
$$
\mathbb{E}_p(x)[tr(\nabla_x \log p_{\theta}(x)) + \frac{1}{2}||\log p_{\theta}(x)||_2^2]
$$
Denoising Score Matching:
$$
\arg \min_{\theta} \mathbb{E}_{p_{\theta}(x)p(\tilde{x}|x)}[||x - \tilde{x}||_2^2]
=\arg \min_{\theta} \frac{1}{2} \mathbb{E}_{p_{\theta}(x)p(\tilde{x}|x)}[||\nabla_{\tilde{x}}\log p_{\theta}(\tilde{x}) - \nabla_{\tilde{x}}\log p(\tilde{x}|x)||_2^2]???
$$
DSM gives the optimal solution: $g^*(\tilde{x}) = \tilde{x} + \sigma^2\nabla_{\tilde{x}}\log p(\tilde{x})$, can then be used to estimate score [2]:
$$
\nabla_{\tilde{x}} \log p_{\tilde{X}}(\tilde{x}) = \frac{g^*(\tilde{x}) - \tilde{x}}{\sigma^2}
$$
in which the distribution is $p_{\tilde{X}}$. Contrast this with [3]:
$$
g^*(\tilde{x}) = \tilde{x} + \sigma^2\nabla_{\tilde{x}}\log p_{X}(\tilde{x}) + o(\sigma^2)
$$
Sliced Score Matching:
$$
\mathbb{E}_{p_v}\mathbb{E}_{p_{data}}[v^T\nabla_x \log p_{\theta}(x)v + \frac{1}{2}(v^T\log p_{\theta}(x))^2]
$$




[1] Generative Modeling by Estimating Gradients of the Data Distribution

[2] On the exact relationship between the denoising function and the data distribution

[3] What Regularized Auto-Encoders Learn from the Data-Generating Distribution