##The DIY Guide to Chainer

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/chainer?pixel)](https://github.com/igrigorik/ga-beacon)

_Please make [Pull Requests](https://github.com/jxieeducation/DIY-Data-Science/pulls) for good resources, or create [Issues](https://github.com/jxieeducation/DIY-Data-Science/issues) for any feedback! Thanks!_

----------


Chainer is a deep learning framework (released June 8, 2015) that is not as well known as Tensorflow or Torch. However, it is extremely intuitive and flexible. This is because Chainer adopts a [Define-BY-Run](http://www.slideshare.net/beam2d/introduction-to-chainer-a-flexible-framework-for-deep-learning/12) model as opposed to a [Define-AND-Run](http://www.slideshare.net/beam2d/introduction-to-chainer-a-flexible-framework-for-deep-learning/9) model. This paradigm gives you immense control of your network, and makes deep nets easy to debug and experiment with.

_[Fun fact](https://twitter.com/ChainerOfficial/status/678087618035236865): Chainer is very popular in the Japanese deep learning community_

### Installation
```
pip install chainer
```
Install [from source](http://docs.chainer.org/en/stable/install.html#install-chainer-from-source) or [with CUDA](http://docs.chainer.org/en/stable/install.html#install-chainer-with-cuda)

----------

###Hello World
#####Introduction 
* Define-BY-Run vs Define-AND-Run - [Short intro](http://docs.chainer.org/en/stable/tutorial/basic.html#core-concept) & [Slides](http://www.slideshare.net/beam2d/introduction-to-chainer-a-flexible-framework-for-deep-learning/9) (slides 9 - 15) & [My explanation](https://gist.github.com/jxieeducation/844adc8ef212d0bdd028429c72e7f5cc)
* Basics concepts - [Overview](http://www.slideshare.net/beam2d/introduction-to-chainer-a-flexible-framework-for-deep-learning/20) (slides 20 - 23)
	* Variable (like Placeholders in TF, Tensors in Torch) - [Example](http://docs.chainer.org/en/stable/tutorial/basic.html#forward-backward-computation) & [Documentation](http://docs.chainer.org/en/stable/reference/core/variable.html)
	* Links (like Layers in Keras and Torch) - [Example](http://docs.chainer.org/en/stable/tutorial/basic.html#links) & [Documentation](http://docs.chainer.org/en/stable/reference/links.html)
	* Neural network - [Example](http://docs.chainer.org/en/stable/tutorial/basic.html#write-a-model-as-a-chain) & [MNIST MLP code](https://github.com/pfnet/chainer/blob/master/examples/mnist/net.py) & [AlexNet code](https://github.com/pfnet/chainer/blob/master/examples/imagenet/alex.py)
	* Optimization - [Example](http://docs.chainer.org/en/stable/tutorial/basic.html#optimizer) & [Documentation](http://docs.chainer.org/en/stable/reference/optimizers.html?highlight=optimizer)
	* Save / Load - [Example](http://docs.chainer.org/en/stable/tutorial/basic.html#serializer)
* Recurrent Neural Network
	* Chainer actually let you break down and play around with RNN
	* [Basic RNN guide](http://docs.chainer.org/en/stable/tutorial/recurrentnet.html) 
	* [Karpathy's Char-RNN example](https://github.com/yusuketomoto/chainer-char-rnn) & [RNNLM example](https://github.com/pfnet/chainer/tree/master/examples/ptb)
	* [LSTM Variants](https://github.com/prajdabre/chainer_examples/blob/master/chainer-1.5/LSTMVariants.py) (how to define new LSTMs like StatefulPeepHoleLSTM)
* Computation graph - [Documentation](http://docs.chainer.org/en/stable/reference/graph.html), [Example visualization](https://twitter.com/chrisemoody/status/626574475237163008)
* Model Zoo - [Documentation](http://docs.chainer.org/en/stable/reference/caffe.html?highlight=zoo), [Code](https://github.com/pfnet/chainer/tree/master/examples/modelzoo)
* GPU support 
	* Done through [CuPy](http://docs.chainer.org/en/stable/cupy-reference/overview.html), as easy as `W.to_gpu()`
	* [Explanation](http://docs.chainer.org/en/stable/tutorial/gpu.html) & [Slides](http://www.slideshare.net/beam2d/introduction-to-chainer-a-flexible-framework-for-deep-learning/29) (slide 29 - 33)
	* [EC2 setup guide](http://sla.hatenablog.com/entry/en_chainer_on_ec2) (5 commands)

#####Instructional Examples
* MNIST - [Walkthrough](http://docs.chainer.org/en/stable/tutorial/basic.html#example-multi-layer-perceptron-on-mnist) & [Code](https://github.com/pfnet/chainer/tree/master/examples/mnist)
* CIFAR-10 - [Different ConvNet examples](https://github.com/mitmul/chainer-cifar10)
* RNNLM - [Char-RNN](https://github.com/yusuketomoto/chainer-char-rnn) & [Word-RNN](https://github.com/pfnet/chainer/tree/master/examples/ptb)
* Word2Vec - [Vanilla implmentation](https://github.com/pfnet/chainer/tree/master/examples/word2vec)
* SVM - [Vanilla implmentation](https://github.com/mitmul/chainer-svm)


###Advanced Nets
#####Autoencoders
* [Regular](http://pc.atsuhiro-me.net/entry/2015/08/18/003402) and [Stacked Denoising](https://gist.github.com/tochikuji/89d5871c19e7decef61b/) autoencoder
* [Convolutional](https://gist.github.com/ktnyt/58e015dd9ff33049da5a) autoencoder
* [Variational](http://nbviewer.jupyter.org/gist/duschendestroyer/a41fcab5f7f9ffa45387) ([alternative](https://github.com/pfnet/chainer/tree/master/examples/vae)) and [Adverserial](https://github.com/musyoku/adversarial-autoencoder) autoencoder
* [Fauxtograph blog](http://multithreaded.stitchfix.com/blog/2015/09/17/deep-style/) (Generating fashion from VAE), [Code](https://github.com/stitchfix/fauxtograph)
* [Binary net](https://github.com/hillbig/binary_net)

#####Convolutional NN
* [ImageNet](https://github.com/pfnet/chainer/tree/master/examples/imagenet), [Karpathy blog](http://karpathy.github.io/2014/09/02/what-i-learned-from-competing-against-a-convnet-on-imagenet/)
* [Convolutional autoencoder](https://gist.github.com/ktnyt/58e015dd9ff33049da5a)
* [DCGAN](https://github.com/mattya/chainer-DCGAN/), [Demo](https://mattya.github.io/chainer-DCGAN/) (Anime face generation), [Sample](https://github.com/mattya/chainer-DCGAN/blob/master/sample1.png)
* [Deep Dream](https://github.com/mattya/chainer-gogh) (Generating Van Gogh paintings), [Sample](https://raw.githubusercontent.com/mattya/chainer-gogh/master/sample_images/im0.png)
* [R-CNN](http://sinhrks.hatenablog.com/entry/2015/07/05/224745), [Faster R-CNN](https://github.com/mitmul/chainer-fast-rcnn), [Sample](https://raw.githubusercontent.com/wiki/mitmul/chainer-fast-rcnn/images/result.jpg)
* [Siamese network](https://github.com/mitmul/chainer-siamese) (contrastive loss)
* [Filter visualization](https://github.com/mitmul/chainer-conv-vis), [Sample](https://raw.githubusercontent.com/wiki/mitmul/chainer-conv-vis/images/result.png)
* [Illustration2Vec](http://illustration2vec.net/papers/illustration2vec-main.pdf) (Converts image to vec, useful in tag generation), [Demo](http://demo.illustration2vec.net/)

#####RNN
* Seq2Seq [dialogue system](https://github.com/kenkov/seq2seq), [machine translation system](https://gist.github.com/odashi/8d21f8fc23c075cd3042)
* [Attention mechanism](https://github.com/odashi/chainer_examples/tree/master/chainer-1.5) (from Graves 2013)
* [Bidirectional RNN](https://groups.google.com/forum/#!topic/chainer/IByadu3z9ps)

#####Reinforcement Learning
* [DQN](https://github.com/ugo-nama-kun/DQN-chainer), [Pong demo](https://www.youtube.com/watch?v=N813o-Xb6S8)
* [Another DQN example](https://github.com/ugo-nama-kun/DQN-chainer), [Platformer demo](https://dl.dropboxusercontent.com/u/59329025/images/20150719_173407.gif)

###[Super Short Feedback Survey](https://docs.google.com/forms/u/0/d/1clz8SPFca-K1aNWFdrrO0QQlSGkLcYyd_F7oRGWq8FA/) (Pretty please!)
