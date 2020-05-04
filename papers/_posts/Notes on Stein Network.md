Notes on Stein Network

Stein Discrepancy:
$$
\begin{align}
S^2 &= \mathbb{E}_{x,y\sim p}[(s_q(x)-s_p(x))^Tk(x,y)(s_q(y)-s_p(y))]\\
&=\mathbb{E}_{x,y\sim p}[s_q(x)^Ts_q(y)k(x,y) + s_q(x)^T\nabla_yk(x,y)
						+ \nabla_xk(x,y)^Ts_q(y) + tr(\nabla_{x,y}k(x,y))]
\end{align}
$$
The optimization problem w.r.t $q$ (assuming to be parameterized by $\theta$) is then equivalent to (dropping the last term):
$$
\mathcal{L} = \mathbb{E}_{x,y\sim p}[s_q(x)^Ts_q(y)k(x,y) + s_q(x)^T\nabla_yk(x,y)
						+ \nabla_xk(x,y)^Ts_q(y)]
$$
For RBF Kernel, we can write the gradient of kernel in closed form:
$$
k(x,y) = \exp (-\frac{||x-y||^2}{2\sigma^2})\\
\nabla_x k(x,y) = k(x,y) \frac{(y-x)}{\sigma^2}\\
\nabla_y k(x,y) = k(x,y) \frac{(x-y)}{\sigma^2}
$$
Implementing $K, \quad K_{ij} = k(x_i, x_j)$. Let $X = [x_1,...,x_n]^T \in R^{n\times d}$
$$
||x_i-x_j||^2 = ||x_i||^2 + ||x_j||^2 - 2 \langle x_i, x_j \rangle
$$


