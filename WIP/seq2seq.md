##The DIY Guide to Seq2Seq

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/seq2seq?pixel)](https://github.com/igrigorik/ga-beacon)

_Please make [Pull Requests](https://github.com/jxieeducation/DIY-Data-Science/pulls) for good resources, or create [Issues](https://github.com/jxieeducation/DIY-Data-Science/issues) for any feedback! Thanks!_

----------

Seq2Seq solves the traditional fixed-size input problem that prevents traditional DNNs from mastering sequence based tasks such as translation and question answering. It has been shown to have state of the art performances in English-French and English-German translations and in responding to short questions. 

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
#####[NEURAL MACHINE TRANSLATION BY JOINTLY LEARNING TO ALIGN AND TRANSLATE](http://arxiv.org/pdf/1409.0473v6.pdf)
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


####Dialog and Q&A
#####[A Neural Conversational Model](http://arxiv.org/pdf/1506.05869v1.pdf)
* The output is now the answer to a question
* Achieves intelligent results from IT Helpdesk and movie subtitles datasets
* [Demo](https://twitter.com/graphific/status/613941774806044672)

#####[Incorporating Copying Mechanism in Sequence-to-Sequence Learning](http://arxiv.org/pdf/1603.06393.pdf)
* Introduces a copy mechanism that decides when words should be repeated from question to answer
* e.g. Q: "My name is Jack!" A: "Hello, Jack!"
* In the attention calculation, create an additional calculation to decide the probability of coping the input word


###Extensions
#####[Order Matters: Sequence to Sequence for Sets](http://arxiv.org/pdf/1511.06391.pdf)
* Input encoding uses a more complicated READ/PROCESS/WRITE procedure, so that the context vector does not depend on the order of the inputs
* Output order is optimized by grid search to find the optimal output