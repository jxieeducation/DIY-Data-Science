##The DIY Guide to Visual Question Answering

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/visualqa?pixel)](https://github.com/igrigorik/ga-beacon)

_Please make [Pull Requests](https://github.com/jxieeducation/DIY-Data-Science/pulls) for good resources, or create [Issues](https://github.com/jxieeducation/DIY-Data-Science/issues) for any feedback! Thanks!_

----------
###Table Of Contents
* [Hello World](#hello-world)
* [Papers](#papers)
* [Datasets](#datasets)

----------

Visual QA is a continuation of deep learning's efforts in image captioning and NLP-based question answering. The goal is for a neural network to take in an image with a question and output good answers. 

![visual qa demo](http://s32.postimg.org/wcjlzzu2t/Screen_Shot_2016_05_08_at_2_42_07_PM.png)

###Hello World

Two interesting events occurred in late 2014. The first would be efforts in image captioning. And the second is in sequence to sequence learning. Visual question answering is the natural combination of the two, a disciplinary born from computer vision and NLP.

####Image Captioning
* Feeding an image through a convnet, then a LSTM 
* [Karpathy Demo](http://stanford.io/1s6fjKi)
![captioning demo](http://s32.postimg.org/ysmzm44xx/Screen_Shot_2016_05_08_at_3_22_42_PM.png)

####Sequence 2 Sequence
* [Seq2Seq Guide](http://bit.ly/1UL8skn)
* Use 1 LSTM to encode the input sequence, use another LSTM to decode to the output
* Initially used for machine translation (English to French)
* Later adopted also as a method to mimic chatbots

Visual QA works by getting a representation of the image through a CNN and also getting a representation of the question through a LSTM. The answer is decoded via a LSTM from the CNN and question LSTM representation.

###Papers
####[Ask Your Neurons: A Neural-based Approach to Answering Questions about Images](http://bit.ly/1SXuhvH)
![ask your neuron image](http://s32.postimg.org/sk9xh9o91/Screen_Shot_2016_05_08_at_3_32_45_PM.png)

* This is the first paper that tries to tackle the visual QA problem
* Doubles accuracy of existing none deep-learning approaches
* Uses a single LSTM network, responsible for both encoding and decoding the question and answer
* Input is the raw concatenation of the word embedding of a word with the representation from the last layer of ImageNet
* Tested on DAQUAR, measure using accuracy and WUPS
* WUPS is like accuracy, but also accounts into similar words (e.g. cat, kitty)
* Introduced the idea of a blind model, so no looking at the picture
* Surprisingly, the blind model produces only slightly worse accuracy than with the CNN input. Meaning that the questions are biased and not diverse enough

####[Are You Talking to a Machine](http://bit.ly/1Xgeaey)
![talking to machine](http://s32.postimg.org/gnmy41091/Screen_Shot_2016_05_08_at_3_34_54_PM.png)

* Divides into 4 components (CNN, question LSTM, answer LSTM, fusing layer)
* The answer LSTM does not use inputs from the CNN and does not decide the output
*  The fusing component (a fully connected net) instead takes the CNN and answer LSTM outputs to decide the next word
* Evaluates output via an adversarial setup
* An answer is deemed good if a human can't figure out that the answer is generated from the model

####[Exploring Models and Data for Image Question Answering](http://bit.ly/21MpTSv)
![exp model architecture](http://s32.postimg.org/fm9c5ijk5/Screen_Shot_2016_05_08_at_6_02_43_PM.png)

* Figured out a way to generate training examples infinitely
* Instead of human curated datasets, create questions from image caption
* Parsed the image caption with the Stanford parser, and made them into questions based on hand crafted rules
* Introduces a similar model architecture, except that the input to the LSTM is the CNN embedding
* In section 4.2 and 4.3 introduces many simple baseline net architectures that are referenced in many other papers


####[Image Question Answering using Convolutional Neural Network](http://bit.ly/1XgeeLx)

![dynamic network demo](http://s32.postimg.org/c6wdnb5ad/Screen_Shot_2016_05_08_at_6_09_30_PM.png)

* This is a very creative paper that is different from others
* Solves only for single answer question, to reduce the main network to solve for a classification problem
* Other architectures have LSTM as the main framework, this paper uses the convnet / regular DNN as the main body
* Question is embedded via GRUs to dynamically control the weights of the second last layer of the CNN / DNN, which is very original
* To predict a large number of weights in the dynamic parameter layer effectively and efficiently, applies hashing trick, which reduces the number of parameters significantly with little impact on network capacity
* Shows that the hashing trick does not deteriorate the accuracy of the classification network

####[Stacked Attention Networks for Image Question Answering](http://bit.ly/1Ty973i)

![stacked attention framework demo](http://s32.postimg.org/8qqxrwkud/Screen_Shot_2016_05_08_at_6_11_37_PM.png)

* Not all parts of the image are relevant to the QA
* Introduces the use of attention layers to select which part of the CNN representation should be passed on
* Most other CNN models use the last fully connected layer in CNN
* This paper takes features from the last pooling layer
* The image is divided into 14x14 sections, and each section has 512 features from the filters
* The LSTM question embeddings and the CNN representations are passed into a stacked attention network 
* Note: use stacked attention network instead of a single attention network to learn complicated relationships 
* The output is a softmax layer that figures out which section of the image is important, which is linearly combined as input to a fully connected classification net


###Datasets
* [DAQUAR](http://bit.ly/1s6fAwH)
* [COCO-QA](http://bit.ly/1T68LUu)
* [VQA](http://bit.ly/1Xgekmj)


###[Super Short Feedback Survey](http://bit.ly/1Txyx1a) (Pretty please!)