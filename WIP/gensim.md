##The DIY Guide to Gensim

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/gensim?pixel)](https://github.com/igrigorik/ga-beacon)

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

Gensim is a very performant python library for NLP projects. It is arguably the most popular library for Word2Vec and Doc2Vec. In addition, it also provides various NLP tools such as LDA, LSI and Random Projection. 

### Installation
```
pip install gensim
easy_install gensim
```

----------

###Hello World
#####Text to Vectors
* For everything else in this library, we first need to transform text to vectors
* [String to vectors tutorial](https://radimrehurek.com/gensim/tut1.html#from-strings-to-vectors)
	* Create a dictionary first that maps words to ids
	* Transform the text into vectors through ```dictionary.doc2bow(texts)```
* [Corpus streaming tutorial](https://radimrehurek.com/gensim/tut1.html#corpus-streaming-one-document-at-a-time)
	* A corpus is simply an iterable where models like Word2Vec can iterate through
	* To train on corpuses larger than memory, we need to stream the corpus content
	* Done through creating an object that has an ```__iter__``` function
#####Models and Transformation
* Models (e.g. LsiModel, Word2Vec) are built / trained from a corpus
* Transformations (e.g. ```corpus_topics = LsiModel[corpus]```) are functions applied to corpuses
* [Transformation interface tutorial](https://radimrehurek.com/gensim/tut2.html#transformation-interface)
	* Must build a model first (e.g. ```models.LsiModel(corpus_tfidf)```)
	* Then apply the model and transform corpuses
	* The rest of the section is about different transformations
#####
