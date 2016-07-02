# Hybrid Recommender System Based On Autoencoders

[Arxiv Link](https://arxiv.org/pdf/1606.07659v1.pdf)

### Application
* Slightly better performance than Matrix Factorization for recommender system
* Provides a solution for the cold start problem via encoding side information

### Summary
* Instead of factorizing users and items to latent vectors, construct stack denoising autoencoders for the users and items
* Provides a loss function specifically for denoising autoencoders that breaks RMS into 2 terms: the uncorrupted and the corrupted inputs
* The weight on the uncorrupted input helps with the reconstruction; the weight on the corrupted input helps train the denoising net
* Since the users and items are sparse matrices, encode the entries as 0 in the input layer of the autoencoder, but do not account of those entries in the loss
* Side information is usually added into the input layer; however, to ensure that the side information is incorporated, concat the side information in every layer to ensure that the network uses the side information
* Using the item autoencoders seem to generate the most lift and learns to incorporate the information best for the MovieLens-1M/10M/20M experiments
