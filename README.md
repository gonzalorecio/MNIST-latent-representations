# tensorflow-mnist-manifolds

Exploration of different dimensionality reduction techniques on the MNIST dataset. The objective is to reduce MNIST data samples to a 2-dimensional representation and analyze the new representation among several appreaches:
 - Variational AutoEncoders (VAE)
 - Dense NN and CNN classifiers
 - Linear approaches: PCA, LDA
 - Non-linear approaches: UMAP, t-SNE


## VAE latent representations
Two different VAEs are tested: one using flat pixel features (only Dense layers), and another using 2d images as input (using Conv2d layers).
- Dimensionality reduction (2D representation), z-dim: 
    - We observe that data samples are embedded to a latent representation where similar classes (e.g. 0 and 6) have a close representation (near in distance) in the latent 2d space.

<p float="left">
    <img src="imgs/latent_VAE_flat.png" width="49%"/>
    <img src="imgs/latent_VAE_CNN.png" width="49%"/>
</p>

- Learnt representations from VAEs (variation of _mu_ and _log_var_ on the axis)
    - Surprisingly, using flat features can lead to good VAE latent representations.

<p float="left">
    <img src="imgs/repr_VAE_flat.png" width="49%"/>
    <img src="imgs/repr_VAE_CNN.png" width="49%"/>
</p>

## NN and CNN classifiers
A feed-forward neural network (shallowing flattened pixels) and a CNN (taking 2d images as input), both containing an inner layer with 2 neurons, are trained to classify the images into numbers. We take a look at the 2-neuron layer to observe which compressed representation each network has learnt.
- Learnt representations after training: Feed-forward NN (flat features) vs. CNN (2D features):

<p float="left">
    <img src="imgs/latent_NN.png" width="49%"/>
    <img src="imgs/latent_CNN.png" width="49%"/>
</p>

- Evolution of the learned MNIST manifold (2D latent space) along batches while learning classification task of the feed-forward NN. We can observe how the neural network tries to find the most suitable compressed 2D representation to easily discriminate the different categories, making the datasamples almost linearly separable (visually better than VAE latent representations):

<img src="imgs/representation_NN_2.gif" width="70%"/>




## Linear dimensionality reduction approaches
- PCA

<p float="left">
    <img src="imgs/pca.png" width="53%"/>
    <img src="imgs/pca-3d.png" width="44%"/>
</p>

- LDA

<p float="left">
    <img src="imgs/lda.png" width="53%"/>
    <img src="imgs/lda-3d2.png" width="46%"/>
</p>

## Non-linear dimensionality reduction approaches


- UMAP

<img src="imgs/umap.png" width="70%"/>

- t-SNE

<img src="imgs/tsne.png" width="70%"/>

## Conclusions

- Manifolds and latent representation learnt by NN and CNN classifiers is the since the networks have the  specific task of class separation (at least more interpretable than VAEs).
- Linear approaches struggle to find a good low-dimensional representation.
- UMAP provides interesting embeddings, and helps to easily identify outliers with acceptable computation time.
