##The DIY Guide to Seq2Seq

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/seq2seq?pixel)](https://github.com/igrigorik/ga-beacon)

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

Seq2Seq solves the traditional fixed-size input problem that prevents traditional DNNs from mastering sequence based tasks such as translation and question answering. It has been shown to have state of the art performances in English-French and English-German translations and in responding to short questions. 

![Generated dialogue](http://s32.postimg.org/6e20by8v9/Screen_Shot_2016_05_01_at_9_29_05_AM.png)

##Hello World

Seq2Seq was first introduced in late 2014 by 2 papers ([Sequence to Sequence Learning with Neural Networks](#sequence-to-sequence-learning-with-neural-networks) and [Learning Phrase Representations using RNN Encoder–Decoder for Statistical Machine Translation](#learning-phrase-representations-using-rnn-encoderdecoder-for-statistical-machine-translation)) from Google Brain and Yoshua Bengio's group. The two papers took a similar approach in machine translation, in which Seq2Seq was developed upon.

###Main Idea

Seq2Seq uses RNNs (usually LSTMs) to map an input sequence to an output sequence through encoding the input and then decoding the output. 

![seq2seq diagram](https://i.gyazo.com/d1d750f3b56f9b8948f42f8273f7a36a.png)

For instance, "A B C EOS" can be mapped to "W X Y Z EOS" (EOS = End of Sentence)

####Encoding
![encoding diagram](http://s32.postimg.org/mtvq063j9/Screen_Shot_2016_05_01_at_9_21_55_AM.png)

The variable length input sequence transformed by the encoder RNN into the context vector (**c**). **c** is usually the last hidden state of the RNN or a weighed sum of the hidden states.

####Decoding
![decoding diagram](http://s32.postimg.org/nad9blzs5/Screen_Shot_2016_05_01_at_9_23_18_AM.png)

The decoder RNN unfolds **c**. This is usually done by a greedy approach of feeding back the word with the highest probability or by a beam search which looks at multiple words before determining the output sequence. 

For more information about encoding or decoding, refer to [Incorporating Copying Mechanism in Sequence-to-Sequence Learning](http://arxiv.org/pdf/1603.06393.pdf) section 2.1. 

#####[Sequence to Sequence Learning with Neural Networks](http://arxiv.org/pdf/1409.3215v3.pdf)
![Sequence diagram](http://s32.postimg.org/trkq2av6t/Screen_Shot_2016_05_01_at_9_26_12_AM.png)
* Recommends reversing the input sequence ("ABC" is entered as "CBA")
* Explains that backpropagation has an easier time "establishing communication" between the source sentence and the target sentence
* Achieves state of the art score on English-French translation, beats state of the art score if the output is rescored

#####[Learning Phrase Representations using RNN Encoder–Decoder for Statistical Machine Translation](http://arxiv.org/pdf/1406.1078.pdf)
* Introduces a simpler version of LSTM 
* Notes that the performance deteriorates rapidly as the length of an input sentence increases

####Attention Mechanism
![Attention diagram](https://camo.githubusercontent.com/0e2e4e5fb2dd47846c2fe027737a5df5e711df1b/687474703a2f2f6936342e74696e797069632e636f6d2f6132727733642e706e67)
#####[Neural Machine Translation By Jointly Learning To Align And Translate](http://arxiv.org/pdf/1409.0473v6.pdf)
* Introduces the attention mechanism
* Proposes that the fixed length embedding is the bottleneck
* Instead of generating a fixed size context vector, creates a variable sized list of hidden states
* Replaces encoder with a bidirectional RNN, generates annotation **h_i** for input **x_i**
* Each annotation **h_i** contains information about the whole input sequence with emphasis on the i-th word
* The decoder RNN decodes context vector **c_i** which is a weighed combination of annotations **h**


###Applications
####Machine Translation
#####[Sequence to Sequence Learning with Neural Networks](#sequence-to-sequence-learning-with-neural-networks) 
#####[Learning Phrase Representations using RNN Encoder–Decoder for Statistical Machine Translation](#learning-phrase-representations-using-rnn-encoderdecoder-for-statistical-machine-translation)

#####[Effective Approaches to Attention-based Neural Machine Translation](http://stanford.edu/~lmthang/data/papers/emnlp15_attn.pdf)
- Focuses on improving the attention mechanism proposed from [the attention paper above](#neural-machine-translation-by-jointly-learning-to-align-and-translate)
- Defines a global attention model that is a simplified derivation
- Defines a local attention model that focuses only on a small subset of the source positions per target word to reduce computation for long inputs

#####[Multi-Task Sequence to Sequence Learning](http://arxiv.org/pdf/1511.06114.pdf)
![many to one](http://s32.postimg.org/mna9f96xx/Screen_Shot_2016_05_01_at_9_30_27_AM.png)
- Trains the same encoder and/or decoder on many different tasks at the same time
- Can be done as one (encoder) to many (decoder), many to one and many to many for tasks like image captioning and machine translation
- Trains different tasks at the same time, each N minibatches at a time 

####Dialog and Q&A
#####[A Neural Conversational Model](http://arxiv.org/pdf/1506.05869v1.pdf)
* Instead of machine translation, maps input (question) to the output (answer)
* Achieves intelligent results from IT Helpdesk and movie subtitles datasets
* [Demo](https://twitter.com/graphific/status/613941774806044672)

#####[Neural Responding Machine for Short-Text Conversation](https://www.aclweb.org/anthology/P/P15/P15-1152.pdf)
![hybrid model](http://s32.postimg.org/muq4txug5/Screen_Shot_2016_05_01_at_9_31_49_AM.png)
- Built a single-conversation (1 post to 1 reply) training dataset off of Weibo (chinese twitter)
- Used separate embeddings for post and reply, because words had different distributions
- Defines attention based decoding as NRM-local and non-attention based decoding as NRM-global (sec 3.2)
- Creates a hybrid model by combing NRM-local and -global, which naively concats the context vectors (sec 3.3)

#####[Incorporating Copying Mechanism in Sequence-to-Sequence Learning](http://arxiv.org/pdf/1603.06393.pdf)
* Introduces a copy mechanism that decides when words should be repeated from question to answer
* e.g. Q: "My name is Jack!" A: "Hello, Jack!"
* In the attention calculation, create an additional calculation to decide the probability of copying the input word

####Autoencoder and Pretraining
#####[Semi-supervised Sequence Learning](http://arxiv.org/pdf/1511.01432v1.pdf)
- Uses a Seq2Seq autoencoder as a pre-training step to improve stability in training tasks with LSTM such as document classification

###Extensions
#####[Order Matters: Sequence to Sequence for Sets](http://arxiv.org/pdf/1511.06391.pdf)
![READ write](http://s32.postimg.org/t34kkwpyd/Screen_Shot_2016_05_01_at_9_34_23_AM.png)
* Input encoding uses a more complicated READ/PROCESS/WRITE procedure, so that the context vector does not depend on the order of the inputs
* Output order is optimized by grid search to find the optimal output

###Resources
####Datasets
#####Machine Translation
* [WMT15](http://www.statmt.org/wmt15/translation-task.html)
* [Eng-Germ](https://github.com/harvardnlp/seq2seq-attn/tree/master/data)

#####Dialog
* [Cornel Movie Dialog](http://www.mpi-sws.org/~cristian/Cornell_Movie-Dialogs_Corpus.html)
* [Toy dataset](https://github.com/eriche2016/seq2seq-1/tree/master/data)
* [Bible](https://github.com/adamchanson/seq2seq/tree/master/data)

####Code Examples
#####Machine Translation
* [Seq2seq-attention](https://github.com/harvardnlp/seq2seq-attn) (Torch)
* [Seq2seq](https://github.com/ma2rten/seq2seq) (Raw implementation)

#####Dialog
* [Neuralconvo](https://github.com/macournoyer/neuralconvo) (Torch)
* [Seq2seq-1](https://github.com/eriche2016/seq2seq-1) (Torch)
* [Neural-chatbot](https://github.com/inikdom/neural-chatbot) (TF)
* [Seq2seq](https://github.com/adamchanson/seq2seq) (Theano)
* [Debug-seq2seq](https://github.com/nicolas-ivanov/debug_seq2seq) (Keras)
* [Seq2seq](https://github.com/kenkov/seq2seq) (Chainer)
* [Tf_seq2seq_chatbot](https://github.com/nicolas-ivanov/tf_seq2seq_chatbot) (TF)

####Blogs
* Domkaukinen - [part1](http://domkaukinen.com/part-1-implementing-a-seq2seq-chatbot-in-torch/), [part2](http://domkaukinen.com/part-2-implementing-seq2seq-chatbot-resolving-memory-issues/), [part3](http://domkaukinen.com/part-3/)
* Indico - [part1](https://indico.io/blog/sequence-modeling-neuralnets-part1/), [part2](https://indico.io/blog/sequence-modeling-neural-networks-part2-attention-models/)
* WildML - [part1](http://www.wildml.com/2016/04/deep-learning-for-chatbots-part-1-introduction/)

###[Super Short Feedback Survey](https://docs.google.com/forms/u/0/d/1lV80v2z0f2tlolGNLpofEHX6Peu0uiYhxWTs6J61mBg) (Pretty please!)
