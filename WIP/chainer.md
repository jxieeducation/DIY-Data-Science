##The DIY Guide to Chainer

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/chainer?pixel)](https://github.com/igrigorik/ga-beacon)

Chainer is another deep learning library that is not as well known as Tensorflow or Torch. However, it is by far the extremely intuitive and flexible. This is because Chainer adopts a [Define-BY-Run](http://www.slideshare.net/beam2d/introduction-to-chainer-a-flexible-framework-for-deep-learning/12) model as opposed to a [Define-AND-Run](http://www.slideshare.net/beam2d/introduction-to-chainer-a-flexible-framework-for-deep-learning/9) model. This paradigm gives you immense control of your network, and makes deep nets insanely easy to control and debug.

_Fun fact: Chainer is very popular in the Japanese deep learning community_

### Installation
```
pip install chainer
```
[Install from source](http://docs.chainer.org/en/stable/install.html#install-chainer-from-source) or [Install with CUDA](http://docs.chainer.org/en/stable/install.html#install-chainer-from-source)

----------

###Hello World
#####Introduction 
* Define-BY-Run vs Define-AND-Run - [Short explanation](http://docs.chainer.org/en/stable/tutorial/basic.html#core-concept) & [Notes](http://www.slideshare.net/beam2d/introduction-to-chainer-a-flexible-framework-for-deep-learning/9) (slides 9 - 15)
* Basics concepts - [Overview](http://www.slideshare.net/beam2d/introduction-to-chainer-a-flexible-framework-for-deep-learning/20)
	* Variable (like Placeholders in TF, Tensors in Torch) - [Example](http://docs.chainer.org/en/stable/tutorial/basic.html#forward-backward-computation) & [Documentation](http://docs.chainer.org/en/stable/reference/core/variable.html)
	* Links (like Layers in Keras and Torch) - [Example](http://docs.chainer.org/en/stable/tutorial/basic.html#links) & [Documentation](http://docs.chainer.org/en/stable/reference/links.html)
	* Neural network - [Example](http://docs.chainer.org/en/stable/tutorial/basic.html#write-a-model-as-a-chain) & [MNIST MLP code](https://github.com/pfnet/chainer/blob/master/examples/mnist/net.py) & [AlexNet code](https://github.com/pfnet/chainer/blob/master/examples/imagenet/alex.py)
	* Optimization - [Example](http://docs.chainer.org/en/stable/tutorial/basic.html#optimizer) & [Documentation](http://docs.chainer.org/en/stable/reference/optimizers.html?highlight=optimizer)
	* Save / Load - [Example](http://docs.chainer.org/en/stable/tutorial/basic.html#serializer)
* Recurrent Neural Network
	* Chainer actually let you break down and play around with RNN
	* [Walkthrough](http://docs.chainer.org/en/stable/tutorial/recurrentnet.html) & [RNNLM example](https://github.com/pfnet/chainer/tree/master/examples/ptb) & [Karpathy's Char-RNN example](https://github.com/yusuketomoto/chainer-char-rnn)
* GPU support 
	* Done through [CuPy](http://docs.chainer.org/en/stable/cupy-reference/overview.html), As easy as `W.to_gpu()`
	* [Explanation](http://docs.chainer.org/en/stable/tutorial/gpu.html) & [Notes](http://www.slideshare.net/beam2d/introduction-to-chainer-a-flexible-framework-for-deep-learning/29) (slide 29 - 33)

#####Instructional Examples
* MNIST - [Walkthrough](http://docs.chainer.org/en/stable/tutorial/basic.html#example-multi-layer-perceptron-on-mnist) & [Code](https://github.com/pfnet/chainer/tree/master/examples/mnist)
* CIFAR-10 - [Vision model examples](https://github.com/mitmul/chainer-cifar10)
* RNNLM - [Char-RNN](https://github.com/yusuketomoto/chainer-char-rnn) & [Word-RNN](https://github.com/pfnet/chainer/tree/master/examples/ptb)
* Word2Vec - [Vanilla implmentation](https://github.com/pfnet/chainer/tree/master/examples/word2vec)



