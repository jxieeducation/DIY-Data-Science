# Document Context Language Model

* [Arxiv link](http://arxiv.org/pdf/1511.03962v4.pdf)

### Application
* This paper tries to solve the problem of generating and classifying coherent sentences
* Can be used to score coherency

### Summary
* Use the hidden unit of the last word in a sentence as the context vector
* The context vector of the previous sentence is used to generate coherent sentences in the current sentence
* Context-to-Context - Concat the last word and the context of the last sentence as input into the RNN
* Context-to-Output - Combines the hidden unit and the context of the last sentence to produce the output of the RNN
* Attentional - Context vector is produced via the hidden units of the previous sentence RNN 
