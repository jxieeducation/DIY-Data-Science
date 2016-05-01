##The DIY Guide to Seq2Seq

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/seq2seq?pixel)](https://github.com/igrigorik/ga-beacon)

_Please make [Pull Requests](https://github.com/jxieeducation/DIY-Data-Science/pulls) for good resources, or create [Issues](https://github.com/jxieeducation/DIY-Data-Science/issues) for any feedback! Thanks!_

----------

Seq2Seq solves the traditional fixed-size input problem that prevents traditional DNNs from mastering sequence based tasks such as translation and question answering. It has been shown to have state of the art performances in English-French and English-German translations and in responding to short questions. 

###Hello World

Seq2Seq was first introduced in late 2014 by 2 papers ([Sequence to Sequence Learning with Neural Networks](http://arxiv.org/pdf/1409.3215v3.pdf) and [Learning Phrase Representations using RNN Encoder–Decoder for Statistical Machine Translation](http://arxiv.org/pdf/1406.1078.pdf)) from Google Brain and Yoshua Bengio's group. The two papers took a similar approach in machine translation, in which Seq2Seq was developed upon.

####Main Idea

Seq2Seq uses RNNs (usually LSTMs) to map an input sequence to an output sequence through encoding the input and then decoding the output. 

![seq2seq diagram](https://i.gyazo.com/d1d750f3b56f9b8948f42f8273f7a36a.png)

For instance, "A B C EOS" can be mapped to "W X Y Z EOS" (EOS = End of Sentence)

#####Encoding
The variable length input sequence transformed by the encoder RNN into the context vector (**c**). **c** is usually the last hidden state of the RNN or a weighed sum of the hidden states.

#####Decoding
The decoder RNN unfolds **c**. This is usually done by a greedy approach of feeding back the word with the highest probability or by a beam search which looks at multiple words before determining the output sequence. 

For more information about encoding or decoding, refer to [Incorporating Copying Mechanism in Sequence-to-Sequence Learning](http://arxiv.org/pdf/1603.06393.pdf) section 2.1. 

#####[Sequence to Sequence Learning with Neural Networks](http://arxiv.org/pdf/1409.3215v3.pdf) by Sutskever et al.
* Recommends reversing the input sequence ("ABC" is entered as "CBA")
* Explains that backpropagation has an easier time "establishing communication" between the source sentence and the target sentence
* Achieves state of the art score on English-French translation, beats state of the art score if the output is rescored

#####[Learning Phrase Representations using RNN Encoder–Decoder for Statistical Machine Translation](http://arxiv.org/pdf/1406.1078.pdf) by Cho et al.
* Introduces a simpler version of LSTM 
* Notes that the performance deteriorates rapidly as the length of an input sentence increases



