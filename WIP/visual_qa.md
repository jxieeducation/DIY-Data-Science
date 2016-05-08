##The DIY Guide to Visual Question Answering

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/visualqa?pixel)](https://github.com/igrigorik/ga-beacon)

_Please make [Pull Requests](https://github.com/jxieeducation/DIY-Data-Science/pulls) for good resources, or create [Issues](https://github.com/jxieeducation/DIY-Data-Science/issues) for any feedback! Thanks!_

----------
###Table Of Contents
* [Main Idea](#main-idea)
* [Applications](#applications)
* [Resources](#resources)
	* [Datasets](#datasets)
	* [Code Examples](#code-examples)
	* [Blogs](#blogs)

----------

Visual QA is a continuation of deep learning's efforts in image captioning and NLP-based question answering. The goal is for a neural network to take in an image with a question and output good answers. 

![visual qa demo](http://s32.postimg.org/wcjlzzu2t/Screen_Shot_2016_05_08_at_2_42_07_PM.png)

<a href="http://bit.ly/1OghkHZ" target="_blank">![demo button](http://3.bp.blogspot.com/-Zmp5pJPF5DQ/VDyqz1K4c5I/AAAAAAAAALA/lYa7IJqGOwQ/s1600/demo.png)
</a>

###Hello World

Two interesting events occurred in late 2014. The first would be efforts in image captioning. And the second is in sequence to sequence learning. Visual question answering is the natural combination of the two, a disciplinary born from computer vision and NLP.

####Image Captioning
* Feeding an image through a convnet, then a LSTM 
* [Karpathy Demo](http://cs.stanford.edu/people/karpathy/deepimagesent/)
![captioning demo](http://s32.postimg.org/ysmzm44xx/Screen_Shot_2016_05_08_at_3_22_42_PM.png)

####Sequence 2 Sequence
* [Seq2Seq Guide](https://github.com/jxieeducation/DIY-Data-Science/blob/master/research/seq2seq.md)
* Use 1 LSTM to encode the input sequence, use another LSTM to decode to the output
* Initially used for machine translation (English to French)
* Later adopted also as a method to mimic chatbots

Visual QA works by getting a representation of the image through a CNN and also getting a representation of the question through a LSTM. The answer is decoded via a LSTM from the CNN and question LSTM representation.

![ask your neuron image](http://s32.postimg.org/sk9xh9o91/Screen_Shot_2016_05_08_at_3_32_45_PM.png)

####[Ask Your Neurons: A Neural-based Approach to Answering Questions about Images](http://arxiv.org/pdf/1505.01121.pdf)
* This is the first paper that tries to tackle the visual QA problem
* Doubles accuracy of existing none deep-learning approaches
* Uses a single LSTM network, responsible for both encoding and decoding the question and answer
* Input is the raw concatenation of the word embedding of a word with the representation from the last layer of ImageNet
* Tested on DAQUAR, measure using accuracy and WUPS
* WUPS is like accuracy, but also accounts into similar words (e.g. cat, kitty)
* Introduced the idea of a blind model, so no looking at the picture
* Surprisingly, the blind model produces only slightly worse accuracy than with the CNN input. Meaning that the questions are biased and not diverse enough

![talking to machine](http://s32.postimg.org/gnmy41091/Screen_Shot_2016_05_08_at_3_34_54_PM.png)
####[Are You Talking to a Machine](http://arxiv.org/pdf/1505.05612.pdf)
* Divides into 4 components (CNN, question LSTM, answer LSTM, fusing layer)
* The answer LSTM does not use inputs from the CNN and does not decide the output
*  The fusing component (a fully connected net) instead takes the CNN and answer LSTM outputs to decide the next word
* Evaluates output via an adversarial setup
* An answer is deemed good if a human can't figure out that the answer is generated from the model