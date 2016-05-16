# Tweet2Vec

* [Arxiv link](https://arxiv.org/pdf/1605.03481.pdf)

### Application
* This paper describes a character model and benchmarks against word models for the task of hashtag prediction

### Summary
* Word embeddings are unflexible because Zipfs law means that there would be a large number non-frequent of vocabulary
* Character models have the advantage in that they can deal with noise, mispellings (such as twitter language)
* Uses a bidirectional GRU to encode tweets (characters, then translated via character embeddings)
* The hidden states of the forward and backward GRUs are combined to predict hashtags
* Benchmarks against a word model where unknown words are replaced with the UNKNOWN token
* Performs significantly better 

![tweet demo](http://s32.postimg.org/zdl0gmcxx/Screen_Shot_2016_05_12_at_8_44_24_PM.png)