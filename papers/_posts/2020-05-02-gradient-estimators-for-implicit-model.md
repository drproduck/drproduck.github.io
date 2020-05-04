---
layout: mathpost
---

Gradient Estimators for Implicit Models

<p>
Notation: \( x \in R^{d\times 1} \), \( g(x^k) = \nabla_{x^k} \log q(x^k)\quad x^k \sim q(x) \)

\( G = (\nabla_{x^1}\log q(x^1),...,\nabla^K\log q(x^K))^T \in R^{K\times d}$, $\hat{G}=(\hat{g}(x^1),...,\hat{g}(x^K))^T \)


\( h:R^{d\times 1} \rightarrow R^{d'\times 1}, h(x) = [h_1(x),...,h_{d'}(x)]^T \)
<\p>

<p>
Stein identity:
$$
\begin{equation}
\mathbb{E}_q[h(x)\nabla_x\log q(x)^T + \nabla_x h(x)] = 0
\end{equation}
$$
Note: $\nabla_x \log q(x) \in R^{d\times 1}$, so the term inside the expectation is $R^{d'\times d}$

Inverting Stein identity (with MC estimator):
$$
\begin{equation}
\frac{1}{K} \sum_{k=1}^K -h(x^k)\nabla_{x^k}\log q(x^k)^T + err = \frac{1}{K}\sum_{k=1}^K \nabla_{x^k}h(x^k),\quad x^k \sim q(x)
\label{}
\end{equation}
$$
Note: both terms are $R^{d' \times d}$. $h(x^k)\in R^{d'\times 1}, \nabla_{x^k}\log q(x^k)\in R^{1\times d}$. K is number of MC samples

Let $H = (h(x^1),...,h(x^K)) \in R^{d'\times K}$ and $\langle \nabla, H \rangle = \sum_{k=1}^K \nabla_{x^k}\frac{1}{K}h(x^k) \in R^{d'\times d}$. Equation above becomes:
$$
-\frac{1}{K} HG + err = \langle \nabla, H \rangle
$$
We want to solve for $G$. Its approximation is:
$$
\hat{G}_S = \arg \min ||\langle \nabla, \frac{1}{K} H \rangle + \frac{1}{K}H\hat{G}||^2 + \frac{\eta}{K^2} ||\hat{G}||^2_F = -K(H^TH + \eta I)(H^T \langle \nabla, H \rangle)
$$
The addition of the L2 regularizer makes the problem well-defined.

Note: $H^TH \in R^{K\times K}$, $d'$ can be infinite (as in RBF)

Note: Recall that the solution to the ridge regression problem $\min_B ||Y-XB||^2 + \eta ||B||^2$ is by setting the derivative to 0:
$$
\begin{align}
\nabla_B ||Y-XB||^2+\eta||B||^2 &= \nabla_B Tr[(Y-XB)^T(Y-XB)] + \eta \nabla_B Tr[B^TB]\\
&= -2\nabla_B Tr[Y^TXB] + \nabla_B Tr[B^TX^TXB] + \eta \nabla_B [B^TB]\\
0 &= \nabla_B Tr[B^TX^TXB] -2\nabla_B Tr[Y^TXB] + \eta\nabla_B [B^TB]\\
&= 2X^TXB - 2X^TY + 2\eta B\\
B &= (X^TX + \eta I)^{-1}X^TY
\end{align}
$$
For RBF kernel we have:
$$
\nabla_y \exp(-\gamma ||x-y||^2) = 2\gamma k(x,y)(x-y)
$$
The second term is:
$$
H^T\langle \nabla, H \rangle = \left[ \sum_{i=1}^{K} h(x^1)^T\nabla_{x_i}h(x_i),...,\sum_{i=1}^{K} h(x^K)^T\nabla_{x_i}h(x_i)\right]^T \in R^{K\times d}
$$

</p>
