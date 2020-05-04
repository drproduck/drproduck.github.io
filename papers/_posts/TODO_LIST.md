(1) Update the draft (results so far, settings, tables) 

(2) Chay voi pretrained cho Cauchy

(3) Chay voi noise, rotation (10 d)

(4) CIFAR, CELEB A, SVHN

(5) Generation



Chay decomposed OT



Chay voi mvn mixture. GREAT!

Compute FID?





Yeah



Co the



Em co viet cai generative model cua minh ra chua



Ban chat la vay ne



Em model P(Z) = \sum_{i = 1}^{K} p_{i} f(z| \theta_{i})



May cai parameters thi minh optimize



o day minh can tim cai P(X)



Thanh ra viet thanh P(X) = \int P(X|Z) P(Z)



Cai integral nay co the viet lai thanh



\sum_{i = 1}^{K} \int P(X| z) f(z| \theta_{i}) dz



Tuc la mot mixture model



Voi cai density o moi component la $\int P(X|z) f(z| \theta_{i}) dz$.



Cai nay cung giai thich vi sao chon Cauchy robust



Vi khi nay minh chon $f(z| \theta)$ la Cauchy distribution



Thanh ra robustness o cai latent space



Cung imply duoc cai robustness tren original space