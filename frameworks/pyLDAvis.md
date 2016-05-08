##The DIY Guide to pyLDAvis

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/gensim?pixel)](https://github.com/igrigorik/ga-beacon)

_Please make [Pull Requests](https://github.com/jxieeducation/DIY-Data-Science/pulls) for good resources, or create [Issues](https://github.com/jxieeducation/DIY-Data-Science/issues) for any feedback! Thanks!_

----------

![pyLDAvis logo](https://camo.githubusercontent.com/9322054a979e54f1dc0bf670a853b06db766be9e/687474703a2f2f7777772e6b656e6e79736869726c65792e636f6d2f666967757265732f6c64617669732d7069632e706e67)

###Table Of Contents
* [One Minute Guide](#one-minute-guide)
* [Hello World](#hello-world)
* [Theory](#theory)

----------

###One Minute Guide

LDAvis helps you interpret LDA results by answer 3 questions:

1. What is the meaning of each topic?
2. How prevalent is each topic?
3. How do topics relate to each other?

<a href="http://bit.ly/1OghkHZ" target="_blank">![demo button](http://3.bp.blogspot.com/-Zmp5pJPF5DQ/VDyqz1K4c5I/AAAAAAAAALA/lYa7IJqGOwQ/s1600/demo.png)
</a>

### Installation
```
pip install pyLDAvis
```

----------

###Hello World
_Just a simple code-based intro, theory is covered in the next section_

#####Firing up a notebook
* The UI is available as a notebook or HTML, let's fire up a notebook
* [Install Jupyter](http://bit.ly/21C6L9E), [Running a notebook](http://bit.ly/1Nlh4MR)

#####Train a quick LDA model
* LDAvis is framework agnostic, meaning that we can use any library in python or R
* Gensim - [Setup](http://bit.ly/1QTxjva), then run ```LdaModel(corpus, num_topics=3)```, [Docs](http://bit.ly/1Nlh7IB)
* Scikit-learn - [Example](http://bit.ly/1O1aTh0), [Docs](http://bit.ly/24w0Zf0)
* GraphLab - [Example](http://bit.ly/21C7J5T)
* LDA in R - [Example](http://bit.ly/1QTxlTX)

#####Enable Notebook
* ```pyLDAvis.enable_notebook()```

#####Prepare LDAvis
* pyLDAvis uses the ```prepare``` method to load the LDA models
* Different libraries requires different variations of the ```prepare``` method
* Gensim - ```prepare(model, corpus, dictionary)```, [Source](http://bit.ly/1NlhcMw)
* Scikit-learn - ```prepare(documents, vectorizer, model)```, [Source](http://bit.ly/1T4bKzU)
* GraphLab - ```prepare(model, documents)```, [Source](http://bit.ly/1NlhgvN)
* LDA in R - ```prepare(*args)```, [Example](http://bit.ly/1QTxlTX)
* And voila! A beautiful dashboard! 

#####Interpreting LDAvis
* LDAvis tries to answer 3 important questions
	* What is the meaning of each topic?
		* The blue denotes overall term frequency and the red denotes term frequency within topic
		* To understand the lambda knob, see [Topic Composition](#topic-composition)
	* How prevalent is each topic? The larger the area, the more prevalent the topic
	* How do topics relate to each other? The larger the overlap between two circles, the closer the topics


###Theory

#####[LDA Intro](http://bit.ly/1rxm2w0)

#####Topic Composition
* [Paper](http://stanford.io/1rxm3Af) (see right module)
* Left ```lambda = 0``` means that you value how exclusive a word is to a topic
	* words are purely ranked on ```P(word | topic)```
* Right ```lambda = 1``` means that you value how probable a word is to appear in a topic
	* words are purely ranked on lift ```P(word | topic) / P(word) ```
* The ranking formula is ```lambda * P(word | topic) + (1 - lambda) * lift ``` (see paper section 3.1)

###[Super Short Feedback Survey](http://bit.ly/1Wd78Iw) (Pretty please!)
