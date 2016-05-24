# Explain Images with Multimodal Recurrent Neural Networks

* [Arxiv link](https://arxiv.org/pdf/1410.1090v1.pdf) 
* [Site](http://www.stat.ucla.edu/~junhua.mao/m-RNN.html)

### Application
* Generates image captions
* Retrieval of most relevant sentences to the given image
* Retrieval of most relevant images to the given sentence

![architecture](http://s33.postimg.org/j8nwgesxr/Screen_Shot_2016_05_23_at_7_02_50_PM.png)

### Summary
* 2 word embedding layers are initialized randomly
* Standard recurrent layer
* Multimodal layer that concatenates the RNN output with AlexNet's 7th layer
* Cost function is based on the log perplexity 

![example](http://s33.postimg.org/coa3d34e7/Screen_Shot_2016_05_23_at_7_09_12_PM.png)