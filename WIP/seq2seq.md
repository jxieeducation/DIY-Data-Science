##The DIY Guide to Seq2Seq

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/seq2seq?pixel)](https://github.com/igrigorik/ga-beacon)

_Please make [Pull Requests](https://github.com/jxieeducation/DIY-Data-Science/pulls) for good resources, or create [Issues](https://github.com/jxieeducation/DIY-Data-Science/issues) for any feedback! Thanks!_

----------

Seq2Seq solves the traditional fixed-size input problem thatEffective Approaches to Attention-based Neural Machine Translation prevents traditional DNNs from mastering sequence based tasks such as translation and question answering. It has been shown to have state of the art performances in English-French and English-German translations and in responding to short questions. 

##Hello World

Seq2Seq was first introduced in late 2014 by 2 papers ([Sequence to Sequence Learning with Neural Networks](http://arxiv.org/pdf/1409.3215v3.pdf) and [Learning Phrase Representations using RNN Encoder–Decoder for Statistical Machine Translation](http://arxiv.org/pdf/1406.1078.pdf)) from Google Brain and Yoshua Bengio's group. The two papers took a similar approach in machine translation, in which Seq2Seq was developed upon.

###Main Idea

Seq2Seq uses RNNs (usually LSTMs) to map an input sequence to an output sequence through encoding the input and then decoding the output. 

![seq2seq diagram](https://i.gyazo.com/d1d750f3b56f9b8948f42f8273f7a36a.png)

For instance, "A B C EOS" can be mapped to "W X Y Z EOS" (EOS = End of Sentence)

####Encoding
The variable length input sequence transformed by the encoder RNN into the context vector (**c**). **c** is usually the last hidden state of the RNN or a weighed sum of the hidden states.

####Decoding
The decoder RNN unfolds **c**. This is usually done by a greedy approach of feeding back the word with the highest probability or by a beam search which looks at multiple words before determining the output sequence. 

For more information about encoding or decoding, refer to [Incorporating Copying Mechanism in Sequence-to-Sequence Learning](http://arxiv.org/pdf/1603.06393.pdf) section 2.1. 

#####[Sequence to Sequence Learning with Neural Networks](http://arxiv.org/pdf/1409.3215v3.pdf)
* Recommends reversing the input sequence ("ABC" is entered as "CBA")
* Explains that backpropagation has an easier time "establishing communication" between the source sentence and the target sentence
* Achieves state of the art score on English-French translation, beats state of the art score if the output is rescored

#####[Learning Phrase Representations using RNN Encoder–Decoder for Statistical Machine Translation](http://arxiv.org/pdf/1406.1078.pdf)
* Introduces a simpler version of LSTM 
* Notes that the performance deteriorates rapidly as the length of an input sentence increases

####Attention Mechanism
#####[Neural Machine Translation By Jointly Learning To Align And Translate](http://arxiv.org/pdf/1409.0473v6.pdf)
* Introduces the attention mechanism
* Proposes that the fixed length embedding is the bottleneck
* Instead of generating a fixed size context vector, creates a variable sized list of hidden states
* Replaces encoder with a bidirectional RNN, generates annotation **h_i** for input **x_i**
* Each annotation **h_i** contains information about the whole input sequence with emphasis on the i-th word
* The decoder RNN decodes context vector **c_i** which is a weighed combination of annotations **h**


###Applications
####Machine Translation
#####[Sequence to Sequence Learning with Neural Networks](http://arxiv.org/pdf/1409.3215v3.pdf) 
#####[Learning Phrase Representations using RNN Encoder–Decoder for Statistical Machine Translation](http://arxiv.org/pdf/1406.1078.pdf))

#####[Effective Approaches to Attention-based Neural Machine Translation](http://stanford.edu/~lmthang/data/papers/emnlp15_attn.pdf)
- Focuses on improving the attention mechanism proposed from [the attention paper above](##neural-machine-translation-by-jointly-learning-to-align-and-translate)
- Defines a global attention model that is a simplified derivation
- Defines a local attention model that focuses only on a small subset of the source positions per target word to reduce computation for long inputs

#####[MULTI-TASK SEQUENCE TO SEQUENCE LEARNING](http://arxiv.org/pdf/1511.06114v1.pdf)
- Trains the same encoder and/or decoder on many different tasks at the same time
- Can be done as one (encoder) to many (decoder), many to one and many to many for tasks like image captioning and machine translation
- Trains different tasks at the same time, each N minibatches at a time 

####Dialog and Q&A
#####[A Neural Conversational Model](http://arxiv.org/pdf/1506.05869v1.pdf)
* Instead of machine translation, maps input (question) to the output (answer)
* Achieves intelligent results from IT Helpdesk and movie subtitles datasets
* [Demo](https://twitter.com/graphific/status/613941774806044672)

#####[Neural Responding Machine for Short-Text Conversation](https://www.aclweb.org/anthology/P/P15/P15-1152.pdf)
- Built a single-conversation (1 post to 1 reply) training dataset off of Weibo (chinese twitter)'s
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
* Input encoding uses a more complicated READ/PROCESS/WRITE procedure, so that the context vector does not depend on the order of the inputs
* Output order is optimized by grid search to find the optimal output

###Resources
####Datasets

####Frameworks
#####Torch
#####Tensorflow
#####Keras
