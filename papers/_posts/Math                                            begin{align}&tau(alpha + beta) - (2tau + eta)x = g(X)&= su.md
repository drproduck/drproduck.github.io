$$
\begin{align}
&\tau(\alpha + \beta) - (2\tau + \eta)x = g(X)\\
&= \sum_{ij}c_{ij}x_{ij} + \tau(\sum_i r_i \log \frac{r_i}{a_i} - x + \alpha) + \tau(\sum_j c_j\log \frac{c_j}{b_j} - x + \beta) + \eta\sum_{ij}x_{ij}\log x_{ij} - \eta x\\
0 &= \sum_{ij}c_{ij}x_{ij} + \tau \sum_i r_i \log \frac{r_i}{a_i} + \tau \sum_j c_j \log \frac{c_j}{b_j} + \eta\sum_{ij} x_{ij}\log x_{ij} \\
&= \sum_{ij}c_{ij}\tilde{x}_{ij} + \tau \sum_i \tilde{r}_i \log \frac{r_i}{a_i} + \tau \sum_j \tilde{c}_j \log \frac{c_j}{b_j} + \eta\sum_{ij} \tilde{x}_{ij}\log x_{ij}\\
&= \sum_{ij}c_{ij}\tilde{x}_{ij} + \tau \sum_i \tilde{r}_i \log \frac{\tilde{r}_i}{\tilde{a}_i} + \tau \sum_j \tilde{c}_j \log \frac{\tilde{c}_j}{\tilde{b}_j} + \eta\sum_{ij} \tilde{x}_{ij}\log \tilde{x}_{ij} + (2\tau + \eta)\log x - \tau \log a - \tau \log b\\
&\tau \log a + \tau \log b + 2\eta \log n \ge (2\tau + \eta)\log x \\
& (ab)^{\frac{\tau}{2\tau + \eta}} \times n ^{\frac{2\eta}{2\tau+\eta}} \ge x^*
\end{align}
$$

where $r_i = \sum_j x_{ij}$, $c_j = \sum_i x_{ij}$