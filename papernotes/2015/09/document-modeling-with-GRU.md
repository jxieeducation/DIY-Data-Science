# Document Modeling with Gated Recurrent Neural Network for Sentiment Analysis

* [Link](http://www.emnlp2015.org/proceedings/EMNLP/pdf/EMNLP167.pdf)

### Application
* Creates embeddings for documents, which can be further utilized for tasks such as sentiment analysis

### Summary
* Principle of compositionality: the meaning of a long expression comes from meaning of constituents
* Divides the document embedding task into 2 parts: 1. create sentence embeddings 2. create document embeddings 
* Sentence embeddings use CNN or LSTM of word embeddings (average is used to fix the CNN size)
* Document embeddings are created via GRUs on sentence embeddings
* Trained the whole net together via sentiment classification / rating predictions

![diagram](http://s32.postimg.org/n3m6n52th/Screen_Shot_2016_05_12_at_8_00_25_PM.png)