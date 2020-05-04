# K-means initialization

### K-means ++

The well-known K-means++ returns an $O(\log k)$  approximation in expectation:
$$
\mathbb{E} (\phi_{++}) \le 8(\ln k + 2) \phi_{opt}
$$
The procedure is as follows:

1. Choose a datapoint uniformly as the first center.
2. For each data point, compute $D(x)$ the distance from $x$ to the nearest center already chosen. Choose the next center according to the probability $\frac{D(x)^2}{\sum_{x' \in \mathcal{X}} D(x')^2}$

3. Add the new center to the set, if fewer than $k$ centers have been chosen, go to step 1.

K-means ++ requires computing $O(n)$ distances at step 2 and is not parallelizable. 



### Scalable K-means ++

The algorithm also has $O(\log k)$ guarantee. It hints on the trade-off in number of sequential steps vs. number of oversampled centers.

1. Choose the first center uniformly. Compute $\phi_1$
2. For i = 2 to $O(\log \phi_1)$, for each datapoint x (independently), add it to the center set with probability $\frac{L \times D(x)^2}{\phi_{i - 1}}$. Compute $\phi_i$ from the new set.
3. re-cluster the (weighted) oversampled centers to reduce to k centers.

For each iteration of step 2, an expected $L$ points are chosen, so that $L \log \phi_1$ are chosen eventually. If we parallelize, we reduce the number of sequential steps but increase the computation at each step (from computing $D(x)$ of oversampled center set). The authors suggest setting the number of iterations constant.  

This method increases complexity by $O(L)$ for reach iteration. It maybe good if a lot of computation is available and $k$ is large. In my test cases I only need small $k$ though.



Other alternatives are: Fast and Provably Good Seedings for k-Means. This algorithm runs in sub-linear time but is also not parallelizable due to the Markov Chain sampling step.