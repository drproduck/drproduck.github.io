From Variational Autoencoder to Deterministic Autoencoder



VAE: stable training, efficient sampling. 

weaknesses: simplistic prior distributions, over-regularizing KL, decoupled latent space from input => posterior collapse + powerful decoder.

Encoder with fixed variance.



Ex-post density estimation: aftering ae training, train another model to fit the latent.



A bunch of smooth regularization techniques: tikhonov, lipschitz continuity (gradient penalty, spectral normalization), implicit regularization (dropout, batchnorm, adding noise)