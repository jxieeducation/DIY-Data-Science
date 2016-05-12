# Hierarchical Recurrent Neural Network for Document Modeling

[Link](http://www.aclweb.org/anthology/D15-1106)

### Application
* Create embeddings for words, sentences and documents
* Predict sentence ordering, translate whole documents instead of sentence by sentence

### Summary
* Creates a word-level language model (RNNLM) and a sentence-level language model (RNNSLM)
* Trains through hierarchical fashion - HRNNLM
* First train a sentence-level language model, by predicting order of sentences
* Then train the whole network (connect the word-level model to the sentence-level model) by predicting the next word
* The sentence-level language model takes in bag of words of sentence with the hidden state of previous sentences to predict the bag of words of the next sentence
* While predicting the next word, the net takes account of previous sentence history and previous word history
