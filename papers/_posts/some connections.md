Why SGD on GMM Maximum Likelihood sucks???

![image-20191203120414331](/home/khiem/.config/Typora/typora-user-images/image-20191203120414331.png)



The following relationships are due to convexity of KL:
$$
\sum_i \frac{1}{N} w_j KL(q(z|x_i), p_j(z)) \ge \sum_i \frac{1}{N}KL(q(z|x_i), p(z)) \ge KL(q(z), p(z))
$$
The following can be proved using log-sum inequality:
$$
\sum_i \frac{1}{N} w_j KL(q(z|x_i), p_j(z)) \ge \inf_{\Pi(\frac{1}{N}, w)}\sum_{i,j} \pi_{ij} KL(q(z|x_i), p_j(z)) \ge  KL(q(z), p(z))
$$
Proof:

The first inequality can be seen by taking $\pi_{ij} = \frac{1}{N}w_j$.

Recall the log-sum inequality:
$$
\sum_i a_i \log \frac{a_i}{b_i} \ge (\sum_i a_i) \log \frac{\sum_i a_i}{\sum_i b_i}
$$
We have:
$$
\sum_i \sum_j \pi_{ij} q(z|x_i) \log \frac{\pi_{ij}q(z|x_i)}{\pi_{ij}p_j(z)} \ge \sum_i \frac{1}{N}q(z|x_i) \log \frac{{\frac{1}{N}}q(z|x_i)}{\sum_j \pi_{ij}p_j(z)} \ge q(z) \log \frac{q(z)}{\sum_i \sum_j \pi_{ij}p_j(z)} \ge q(z) \log \frac{q(z)}{\sum_j w_j p_j(z)}
$$
The last denominator is indeed $p(z)$



What about the relationship between $\sum_i \frac{1}{N} KL(q(z|x_i), p(z))$ and $\inf_{\Pi(\frac{1}{N}, w)}\sum_{i,j} \pi_{ij} KL(q(z|x_i), p_j(z))$?

Proof:


$$
\begin{align*}
\sum_i \sum_j \pi_{ij} q(z|x_i) \log \frac{\pi_{ij}q(z|x_i)}{\pi_{ij}p_j(z)} \ge \sum_i \frac{1}{N}q(z|x_i) \log \frac{{\frac{1}{N}}q(z|x_i)}{\sum_j \pi_{ij}p_j(z)} \\
= \sum_i \frac{1}{N}q(z|x_i)\log \frac{q(z|x_i)}{\sum_j \pi_{ij}p_j(z)} - q(z)\log N \\
\ge \sum_i \frac{1}{N} q(z|x_i)\log \frac{q(z|x_i)}{\sum_j w_j p_j(z)} - q(z)\log N
\end{align*}
$$
Integrating over $z$ and using the infimum of $\pi$ have have:
$$
\inf_{\Pi(\frac{1}{N}, w)}\sum_{i,j} \pi_{ij} KL(q(z|x_i), p_j(z)) \ge \sum_i \frac{1}{N} KL(q(z|x_i), p(z)) - \log N
$$
On the other hand, we have \sum_

