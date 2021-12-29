# tensorflow-mnist-manifolds
Exploration of different dimensionality reduction techniques on the MNIST dataset.
 - Variational AutoEncoders (VAE)
 - Dense NN and CNN classifiers
 - Linear approaches: PCA, LDA
 - Non-linear approaches: UMAP, t-SNE


## VAE latent representations

- Dimensionality reduction (2D representation)

<p float="left">
    <img src="imgs/latent_VAE_flat.png" width="49%"/>
    <img src="imgs/latent_VAE_CNN.png" width="49%"/>
</p>

- Learnt representations from VAEs (variation of _mu_ and _log_var_ on the axis).

<p float="left">
    <img src="imgs/repr_VAE_flat.png" width="48%"/>
    <img src="imgs/repr_VAE_CNN.png" width="48%"/>
</p>

## NN and CNN classifiers

Learned MNIST manifold (2D latent space) along batches while learning classification task. We can observe how the neural network tries to fing the most suitable 2D representation to easily discriminate the different categories (probabli better than VAE):

<img src="imgs/representation_NN_2.gif" width="60%"/>


### Flat features vs. 2D features (convolutional)

<p float="left">
    <img src="imgs/latent_NN.png" width="49%"/>
    <img src="imgs/latent_CNN.png" width="49%"/>
</p>

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

<img src="imgs/umap.png" width="80%"/>

- t-SNE

<img src="imgs/tsne.png" width="80%"/>

## Conclusions

- Manifolds and latent representation learnt by NN and CNN classifiers is the since the networks have the  specific task of class separation (at least more interpretable than VAEs).

- UMAP provides interesting embeddings, and helps to easily identify outliers with acceptable computation time.
