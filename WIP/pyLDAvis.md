##The DIY Guide to Gensim

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/gensim?pixel)](https://github.com/igrigorik/ga-beacon)

_Please make [Pull Requests](https://github.com/jxieeducation/DIY-Data-Science/pulls) for good resources, or create [Issues](https://github.com/jxieeducation/DIY-Data-Science/issues) for any feedback! Thanks!_

----------

![pyLDAvis logo](https://camo.githubusercontent.com/9322054a979e54f1dc0bf670a853b06db766be9e/687474703a2f2f7777772e6b656e6e79736869726c65792e636f6d2f666967757265732f6c64617669732d7069632e706e67)

###Table Of Contents
* [Hello World](#hello-world)
* [Theory](#theory)

----------

It's not easy to interpret LDA. Most of us guess the topics by eye balling the most probable words, and make sense of the topics by looking for common words. LDAvis makes this insanely easy and provides a great interactive UI. And the best of all, LDAvis requires less than 5 lines of code. [Demo](http://cpsievert.github.io/LDAvis/newsgroup/vis/#topic=0&lambda=1&term=)


### Installation
```
pip install pyLDAvis
```

----------

###Hello World
_Just a simple code-based intro, theory is covered in the next section_

#####Firing up a notebook
* The UI is available as a notebook or HTML, let's use the notebook first
* [Install Jupyter](http://jupyter.readthedocs.io/en/latest/install.html#installing-jupyter-i-already-have-python), [Running a notebook](http://jupyter.readthedocs.io/en/latest/running.html#running-the-notebook)

#####Train a quick LDA model
* LDAvis follows the BYOM - Bring your own model philosophy, so we can pretty much use any framework in python or R
* Gensim - [Make a corpus](https://radimrehurek.com/gensim/tut1.html), then run ```LdaModel(corpus, num_topics=3)```, [Docs](https://radimrehurek.com/gensim/models/ldamodel.html)
* Scikit-learn - [Code](http://scikit-learn.org/stable/auto_examples/applications/topics_extraction_with_nmf_lda.html), [Docs](http://scikit-learn.org/stable/modules/generated/sklearn.decomposition.LatentDirichletAllocation.html)
* GraphLab - [Notebook](http://nbviewer.jupyter.org/github/bmabey/pyLDAvis/blob/master/notebooks/GraphLab.ipynb#topic=7&lambda=0.41&term=)
* LDA in R - [Load model into a python dictionary](http://nbviewer.jupyter.org/github/bmabey/pyLDAvis/blob/master/notebooks/pyLDAvis_overview.ipynb#BYOM---Bring-your-own-model)

#####Prepare LDAvis
* First enable notebook display ```pyLDAvis.enable_notebook()```
* pyLDAvis uses the ```prepare``` method to load the LDA models
* Different libraries use a different variation of the ```prepare``` method
* Gensim - ```prepare(model, corpus, dictionary)```, [Source](https://github.com/bmabey/pyLDAvis/blob/master/pyLDAvis/gensim.py#L52)
* Scikit-learn - ```prepare(documents, vectorizer, model)```, [Source](https://github.com/bmabey/pyLDAvis/blob/master/pyLDAvis/sklearn.py#L21)
* GraphLab - ```prepare(model, documents)```, [Source](https://github.com/bmabey/pyLDAvis/blob/master/pyLDAvis/graphlab.py#L46)
* LDA in R - ```prepare(*args)```, [Example](http://nbviewer.jupyter.org/github/bmabey/pyLDAvis/blob/master/notebooks/pyLDAvis_overview.ipynb#BYOM---Bring-your-own-model)

#####Interpreting LDAvis
* LDAvis tries to answer 3 important questions
	* What is the meaning of each topic?
	* How prevalent is each topic?
	* How do topics relate to each other?


###Theory

LDAvis is really findings from two papers. One deals with visualizing how topics relate to each other, and the other figures out how to find the most relevant words to represent a topic.

#####Relevance
* [Paper](http://nlp.stanford.edu/events/illvi2014/papers/sievert-illvi2014.pdf)


#####Saliency
* [Paper](http://vis.stanford.edu/files/2012-Termite-AVI.pdf) 
