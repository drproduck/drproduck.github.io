The (unregularized) objective is:
$$
\langle C, P \rangle + \tau KL(P1||a) + \tau KL(P^T1||b)
$$


Let $r_i = (P1)_i$ and $c_j = (P^T1)_j$, then $\sum_i r_i = \sum_j c_j = \sum_{ij}P_{ij} = p$. Differentiating w.r.t. $p_{ij}$ and setting the derivative to 0 we have:
$$
\begin{equation}
c_{ij} + \tau(\log r_i - \log a_i) + \tau(\log c_j - \log b_j) = 0\\
r_i c_j = e^{-c_{ij}/\tau}a_i b_j \quad \forall i,j
\end{equation}
$$
Summing w.r.t $i$ and $j$ we have:
$$
p^2 = \sum_i \sum_j e^{-c_{ij}/\tau}a_ib_j \le \sum_i \sum_j a_i b_j = (\sum_i a_i)(\sum_j b_j)
$$






