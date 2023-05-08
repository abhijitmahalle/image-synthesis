## Description

The goal of this project is to synthesize the image using $\beta$-variational autoencoder. The autoencoder is trained on the MNIST data set and after training, encoder generated images of the digit from the random noise sample from normal distribution.

## What is the $\beta$-Variational Autoencoder?

$\beta$-VAE is a deep unsupervised generative approach a variant of Variational AutoEncoder for disentangled factor learning that can discover the independent latent factors of variation in unsupervised data. A disentangled representation can be defined as one where single latent units of $z$ are sensitive to changes in single generative factors of $X$, while being relatively invariant to changes in other factors. A disentangled model learns independent latent units sensitive to single independent data generative factors. A disentangled representation is therefore factorised and often interpretable, whereby different independent latent units learn to encode different independent ground-truth generative factors of variation in the data.

The difference between $\beta$-VAE and VAE is the use of lagrange multiplier $/beta$ on the KL divergence term in the original VAE formulation. Objective function of $\beta$-VAE is

![1_nvoD_xhYnTCDQBIDB6ywzw (1)](https://user-images.githubusercontent.com/90370308/226409398-4536a9d8-eaab-4519-9e34-f2dd304969ff.png)

$\beta$-VAE attempts to learn a disentangled representation of conditionally independent data generative factors by optimizing a heavily penalizing KL-divergence between the prior and approximating distributions using a hyperparameter $\beta$ > 1. This constraint limits the capacity of $z$, which, combined with the pressure to maximise the log likelihood of the training data $X$, encourages the model to learn the most efficient representation of the data. We assume that the data $x$ has some conditionally independent ground truth factors of generation and the KL-divergence term of the $\beta$-VAE objective function encourages conditional independence in $qφ(z|x)$. Hence higher values of $\beta$ should encourage learning a disentangled representation. The extra pressures coming from high $\beta$ values, however, may create a trade-off between reconstruction fidelity and the quality of disentanglement within the learnt latent representations. Disentangled representations emerge when the right balance is found between information preservation.

## Result

- Validation image at Epoch 0 during training (Ground truth image followed by generated image)
![1](https://user-images.githubusercontent.com/90370308/226411068-e46d6ef8-6ace-4a2b-a0ac-b3eeec3a0032.png)
![2](https://user-images.githubusercontent.com/90370308/226411100-0256afa5-0b01-48e9-be0c-bad01bed40bf.png)

- Validation image at Epoch 100 during training (Ground truth image followed by generated image)
![3](https://user-images.githubusercontent.com/90370308/226412074-a7c06a9a-b7da-4bff-a086-3b6d072e0991.png)
![4](https://user-images.githubusercontent.com/90370308/226412098-eb0d43f9-b72f-4a9e-a2a8-860533e487cf.png)

<!-- - Test images
![test image](https://user-images.githubusercontent.com/90370308/226412534-218ad78b-687b-4274-8ab9-51552d494850.png) -->

- Interpolation of two image by walking in latent space from image 1 to image 2 in 16 steps.
![interpolation_1](https://user-images.githubusercontent.com/90370308/226414289-fe6d59f3-2a79-451e-b624-ab6298cc3148.png)
![interpolation_2](https://user-images.githubusercontent.com/90370308/226414309-7041e15d-78cd-4a02-96d5-c0a888c0a75c.png)
![interpolation_3](https://user-images.githubusercontent.com/90370308/226414333-b3f98493-7386-4f26-91e8-914dad36cc99.png)
![interpolation_4](https://user-images.githubusercontent.com/90370308/226414347-99092bda-83f9-46b8-b0b5-b74941d34e7e.png)

- The cluster of mean of the distribution corrosponding to the input data points. The mean are compressed from 20 dimensions to 2 dimensions for visualization. It is worth noting how mean are random at the epoch 0 and cluster together at epoch 10. 

![Distribution_in_latent_space](https://user-images.githubusercontent.com/90370308/226415030-a97b105a-315b-4a4d-aeb6-2ae256a4123e.png)

## Requirement
Python 2.0 or above

## License

 [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Copyright (c) Feb 2023 Pradip Kathiriya














