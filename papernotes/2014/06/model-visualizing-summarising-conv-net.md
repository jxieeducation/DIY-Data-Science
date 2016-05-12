# Extraction of Salient Sentences from Labelled Documents

* [Arxiv link](http://arxiv.org/pdf/1412.6815v2.pdf) 
* [Code](https://github.com/mdenil/txtnets)

### Application
* This paper introduces a way to create document embeddings
* Classification can be trained on top of the embeddings for sentiment analysis, summarisation and visualization

### Summary
* The word embedding sentence matrix undergoes convolution to create document embeddings
* The problem variable length sentence length poses is solved by K-max pooling
* Convolution generates a single value for all dimensions of the embedding, which reduces parameters
* Visualizations of activations of ConvNets can also be used to visualize activations of text

![summary example](http://s32.postimg.org/t9o56tmth/Screen_Shot_2016_05_11_at_9_13_17_PM.png)