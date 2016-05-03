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
_Just a simple coding intro, theory is covered in the next section_
#####Text to Vectors
* For everything else in this library, we first need to transform text to vectors
* [String to vectors tutorial](https://radimrehurek.com/gensim/tut1.html#from-strings-to-vectors)
	* Create a dictionary first that maps words to ids
	* Transform the text into vectors through ```dictionary.doc2bow(texts)```
* [Corpus streaming tutorial](https://radimrehurek.com/gensim/tut1.html#corpus-streaming-one-document-at-a-time)
	* A corpus is simply an iterable where models like Word2Vec can iterate through
	* To train on corpuses larger than memory, we need to stream the corpus content

#####Models and Transformation
* Models (e.g. LsiModel, Word2Vec) are built / trained from a corpus
* [Transformation interface tutorial](https://radimrehurek.com/gensim/tut2.html#transformation-interface)

#####TF-IDF (Model)
* [Docs](https://radimrehurek.com/gensim/models/tfidfmodel.html), [Source](https://github.com/piskvorky/gensim/blob/develop/gensim/models/tfidfmodel.py)
* [tf-idf scores are normalized](http://stackoverflow.com/questions/9470479/how-is-tf-idf-implemented-in-gensim-tool-in-python) (sum of squares of scores = 1)

#####Phrases (Model)
* Detects words that belong in a phrase, useful for models like Word2Vec ("new", "york" -> "new york")
* [Docs](https://radimrehurek.com/gensim/models/phrases.html), [Source](https://github.com/piskvorky/gensim/blob/develop/gensim/models/phrases.py) (uses bigram detectors underneath)
* [Phrases example on How I Met Your Mother](http://www.markhneedham.com/blog/2015/02/12/pythongensim-creating-bigrams-over-how-i-met-your-mother-transcripts/)

#####LSI (Model)
* [Docs](https://radimrehurek.com/gensim/models/lsimodel.html), [Source](https://github.com/piskvorky/gensim/blob/develop/gensim/models/lsimodel.py) (very standard LSI implementation)
* [How to interpret negative LSI values](https://www.researchgate.net/post/LSA_SVD_How_to_statistically_interpret_negative_values_in_U_and_Vt)
* [Random Projection](https://radimrehurek.com/gensim/models/rpmodel.html) (used as an option to speed up LSI)

#####LDA (Model)
* [Docs](https://radimrehurek.com/gensim/models/ldamodel.html), [Source](https://github.com/piskvorky/gensim/blob/develop/gensim/models/ldamodel.py)
* [Using LDA on Android issue reports](http://christop.club/2014/05/06/using-gensim-for-lda/) (example)

#####Word2Vec (Model)
* [Docs](https://radimrehurek.com/gensim/models/word2vec.html), [Source](https://github.com/piskvorky/gensim/blob/develop/gensim/models/word2vec.py) (very simple interface)
* [Simple word2vec tutorial](http://rare-technologies.com/word2vec-tutorial/) (examples of ```most_similar, similarity, doesnt_match```)

#####Doc2Vec (Model)
* [Docs](https://radimrehurek.com/gensim/models/doc2vec.html), [Source](https://github.com/piskvorky/gensim/blob/develop/gensim/models/doc2vec.py) (Docs are not very good)
* Doc2Vec requires a non-standard corpus (need sentiment label for each document)
* [Great illustration of corpus preparation](https://linanqiu.github.io/2015/10/07/word2vec-sentiment/), [Code](https://github.com/linanqiu/word2vec-sentiments) ([Alternative](https://medium.com/@klintcho/doc2vec-tutorial-using-gensim-ab3ac03d3a1#.nv2lxvbj1))