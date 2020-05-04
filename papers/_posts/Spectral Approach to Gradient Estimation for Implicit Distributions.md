Spectral Approach to Gradient Estimation for Implicit Distributions

By Stein's identity:
$$
\mathbb{E}_q[\psi_j(x)g(x) + \nabla_x \psi_j(x)] = 0
$$
Where $\psi_j(x)$ are the eigenfunctions of $L^2$ ($\psi$ should be in Stein class). $g(x)$ can then be written as:
$$
g(x) = \beta \psi(x)
$$
Where $g(x) = \nabla_x \log q(x) \in R^{d}$, $\beta_i \in R^{d\times \infty}$, $\psi(x) = [\psi_1(x),...,\psi_{\infty}(x)]^T$,

$\psi_j(x)$ is a scalar, the j highest eigenfunction corresponding to $x$ i.e. $\int \psi_i(x)\psi_j(x)q(x)dx = \delta_{ij}$ 

$\beta_{ij}$ is the coefficient of $\nabla_{x_i} \log q(x)$ and $\psi_j(x)$. 

The above gives:
$$
\mathbb{E}_q[\psi(x) \beta \psi(x) + \nabla_x \psi(x)] = 0\\
\beta = \mathbb{E}_q \nabla_x \psi(x)
$$
Since $\mathbb{E}_q[\psi(x)_i\psi(x)_j] = \delta_{ij}$. We need to compute $\nabla_x \psi(x)$:
$$
\mu_j \nabla_x \psi_j(x) = \nabla_x \mathbb{E} [k(x,y)\psi_j(y)]\\
\nabla_x \psi_j(x) = \frac{1}{\mu_j}\mathbb{E}[\nabla_x k(x,y)\psi_j(y)]
$$
Using samples $x_m$ and Nystrom approximated eigen-pairs:
$$
\nabla_x \psi_j(x) \approx \frac{\sqrt{M}}{\lambda_j}\sum_m \nabla_x k(x,x^m)u_{jm}
$$
Plugging in:
$$
\begin{align}
\beta &= \mathbb{E}_{x\sim q}\left[ \left[\frac{\sqrt{M}}{\lambda_1}\sum_m \nabla_x k(x,x^m)u_{1m},...,\frac{\sqrt{M}}{\lambda_{\infty}}\sum_m \nabla_x k(x,x^m)u_{\infty m} \right] \right]\\
\end{align}
$$


Lastly, recall: $\nabla_x k(x, x^m) = -k(x,x^m)\frac{x-x^m}{\sigma^2}$.

Note: In practice we take only the $J$ largest eigen-pairs, and approximate $g(x) = \sum_j \beta_j \nabla_x \psi_j(x)$

