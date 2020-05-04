Stein Discrepancy is Score Matching (and Fisher Divergence)

Recall Stein Identity:
$$
A_P[f] = \nabla f + f \nabla \log P
$$
And for all $f$:
$$
\int A_P[f] dP = 0
$$
Stein Discrepancy as an IPM (second term is Stein Discrepancy, first term is its IPM form):
$$
\sup_{A_P[f]}\left|\int A_P[f]dP - \int A_P[f]dQ\right| = \sup_{f}\left|\int A_P[f]dQ\right|
$$
The space of test/witness functions $A_P[f]$ are functions that satisfy Stein identity. This requires $Pf| = 0$. As such heavy-tailed P may fail.

Stein Discrepancy is Score Matching:
$$
\begin{align}
\sup_{f}\left|\int A_P[f]dQ\right|^2 &= \sup_{f} \left| \int A_P[f] - A_Q[f]dQ \right|^2\\
&= \sup_{f} \left| \int ((\nabla \log P - \nabla \log Q) \cdot f) dQ \right|^2 \\
&= \sup_f \left| \langle (\nabla \log P - \nabla \log Q), f\rangle_{L^2(Q)} \right|^2\\
&= ||(\nabla \log P - \nabla \log Q)||^2_{L^2(Q)}\\
&= \int ||\nabla \log P - \nabla \log Q||^2_2 dQ
\end{align}
$$
Note: the first equality uses $\int A_Q[f]dQ = 0$

Note: the forth equality, think of the usual Euclidean space, what maximizes the dot product for f?