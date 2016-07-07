# Learning Discriminative Features using Encoder/Decoder type Deep
Neural Nets

[Arxiv Link](https://arxiv.org/pdf/1607.01354.pdf)

# Application
* An improvement upon using autoencoders for dimensionality reduction as input for a classifier

# Summary
* One of the first use cases for autoencoders is to do dimensionality reduction
* Autoencoders traditionally are performed as an unsupervised learning task, not designed as an input for a classifier
* It's hard to extract meaningful information: 1) features are sensitive to intra-class differences 2) less sensitive to inter-class differences
* In order to learn inter-class differences, need to focus less on intra-class differences
* Proposes that instead of mapping an input to itself, map an input to the ideal version of the input class

![normal autoencoder](https://s32.postimg.org/8ffs97dzp/Screen_Shot_2016_07_06_at_7_48_37_PM.png)

![new autoencoder](https://s32.postimg.org/wxy1m2cf9/Screen_Shot_2016_07_06_at_7_48_43_PM.png)

* Using the new encoder/decoder, shows better classifier results than PCA, and normal autoencoder, but with a fraction of parameters
