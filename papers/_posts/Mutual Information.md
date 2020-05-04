Mutual Information
$$
\begin{align}
I(X, Z) &=  \int p(x,z) \log \frac{p(x|z)}{p(x)} dx dz\\
&= \int p(x,z) \log p(x|z) dx dz - \int p(x) \log p(x) dx\\
& \ge \int p(z) \left(\int p(x|z) \log p(x|z)dx - \int p(x|z)\log \frac{p(x|z)}{q(x|z)}dx\right) dz + H(p(x))\\
&= \int p(z) p(x|z) \log q(x|z) dx dz + H(p(x))\\
&= \int p(x) p(z|x) \log q(x|z) dx dz + H(p(x))
\end{align}
$$


Mutual information:
$$
I(X, Y) = KL(p(x,y), p(x)p(y)) = \int p(x, y)\log \frac{p(x, y)}{p(x)p(y)}dxdy
$$
The information bottleneck method:

Suppose we want to encoder X -> \tilde{X}.

The rate (average number of bits per message needed) determines the quality of quantization. This number is bounded below by I(X, \tilde{X}).

However, information rate alone is not enough: the rate can always be reduced by throwing away details of the original signal X.

Distortion function: d(X, \tilde{X}) measures the distortion (literally).

larger rate means smaller achievable distortion (more information is preserved)



Rate-Distortion Function: Minimal achievable rate under given constraint on the expected distortion.

![image-20191207203357531](/home/khiem/.config/Typora/typora-user-images/image-20191207203357531.png) 



Information bottleneck: Introducing a relevance variable Y, s.t. I(X; Y) > 0.  The amount of information about Y in \tilde{X} is less than that about Y in X. 

![image-20191207205301048](/home/khiem/.config/Typora/typora-user-images/image-20191207205301048.png)

There is a tradeoff between compression (X and \tilde{X}) and preservation (\tilde{X} and Y). There is no right solution for the tradeoff (\beta):

![image-20191207205722097](/home/khiem/.config/Typora/typora-user-images/image-20191207205722097.png)

The "bottleneck": X -> \tilde{X} -> Y. Compression and Preservation.

~~Comment: for IB is rate-distortion if we take $d(x, \tilde{x}) = KL(p(y|x), p(y|\tilde{x}))$~~



127.0.0.1       localhost
127.0.1.1       noibai
10.100.132.101  hanoi
10.111.191.200  saigon
10.111.191.201  danang
10.111.191.54   haiphong
10.111.191.46   sapa
10.111.191.58   dalat
10.111.191.68   london
10.111.191.88   hue
10.111.191.66   cantho

# The following lines are desirable for IPv6 capable hosts
::1     ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
~                          