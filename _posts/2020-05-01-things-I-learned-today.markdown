---
layout: mathpost
title:  "Things I learned today"
date:   2020-05-01
categories: learning
---

<p>
When back-propagating through a Euclidean distance matrix where each entry is 
\[||x - y||_{2} = \sqrt{||x||^2 - 2\langle x, y \rangle + ||y||^2}\]
because \( d\sqrt{x} = \frac{1}{\sqrt{x}} dx\), \( d\sqrt{x}(0) \rightarrow \infty \). A solution is to use add a small value (e.g. 1e-16), or to use squared Euclidean distance when possible.
<\p>


<p>
A comparative study of efficient initialization methods for the k-means clustering algorithm: Comparing k-means initialization methods. Surprisingly k-means++ is not recommended (near the Conclusion). Greedy k-means is recommended for small (<1000) datasets.
<\p>
