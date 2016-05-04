##The DIY Guide to Gensim

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/gensim?pixel)](https://github.com/igrigorik/ga-beacon)

_Please make [Pull Requests](https://github.com/jxieeducation/DIY-Data-Science/pulls) for good resources, or create [Issues](https://github.com/jxieeducation/DIY-Data-Science/issues) for any feedback! Thanks!_

----------

![gensim logo](http://trevor-smith.github.io/images/gensim.png)

###Table Of Contents
* [Hello World](#hello-world)
* [Theory](#theory)
* [Advanced Features](#advanced-features)

----------

Gensim is a very performant python library for NLP projects. It is arguably the most popular library for Word2Vec and Doc2Vec. In addition, it also provides various NLP tools such as LDA, LSI and Random Projection. 

### Installation
```
pip install gensim
easy_install gensim
```

----------

###Hello World
_Just a simple code-based intro, theory is covered in the next section_
#####Text to Vectors
* We first need to transform text to vectors
* [String to vectors tutorial](https://radimrehurek.com/gensim/tut1.html#from-strings-to-vectors)
	* Create a dictionary first that maps words to ids
	* Transform the text into vectors through ```dictionary.doc2bow(texts)```
* [Corpus streaming tutorial](https://radimrehurek.com/gensim/tut1.html#corpus-streaming-one-document-at-a-time) (For very large corpuses)

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
* [Example with Android issue reports](http://christop.club/2014/05/06/using-gensim-for-lda/), [Another example](https://rstudio-pubs-static.s3.amazonaws.com/79360_850b2a69980c4488b1db95987a24867a.html), [Another example](http://brandonrose.org/clustering#Latent-Dirichlet-Allocation)

#####Word2Vec (Model)
* [Docs](https://radimrehurek.com/gensim/models/word2vec.html), [Source](https://github.com/piskvorky/gensim/blob/develop/gensim/models/word2vec.py) (very simple interface)
* [Simple word2vec tutorial](http://rare-technologies.com/word2vec-tutorial/) (examples of ```most_similar, similarity, doesnt_match```)

#####Doc2Vec (Model)
* [Docs](https://radimrehurek.com/gensim/models/doc2vec.html), [Source](https://github.com/piskvorky/gensim/blob/develop/gensim/models/doc2vec.py) (Docs are not very good)
* Doc2Vec requires a non-standard corpus (need sentiment label for each document)
* [Great illustration of corpus preparation](https://linanqiu.github.io/2015/10/07/word2vec-sentiment/), [Code](https://github.com/linanqiu/word2vec-sentiments) ([Alternative](https://medium.com/@klintcho/doc2vec-tutorial-using-gensim-ab3ac03d3a1#.nv2lxvbj1), [Alternative 2](https://districtdatalabs.silvrback.com/modern-methods-for-sentiment-analysis))
* [Doc2Vec on customer review](http://multithreaded.stitchfix.com/blog/2015/03/11/word-is-worth-a-thousand-vectors/) (example)

----------


###Theory

#####TFIDF
* [Best explanation](http://michaelerasm.us/tf-idf-in-10-minutes/), [Paper](https://www.cs.rutgers.edu/~mlittman/courses/ml03/iCML03/papers/ramos.pdf)

#####LSI
* [LSI intuition](https://technowiki.wordpress.com/2011/08/27/latent-semantic-analysis-lsa-tutorial/), [Step by step walkthrough](http://www1.se.cuhk.edu.hk/~seem5680/lecture/LSI-Eg.pdf)
* [Math approach](http://www.engr.uvic.ca/~seng474/svd.pdf)

#####LDA
* [Intuition](https://tedunderwood.com/2012/04/07/topic-modeling-made-just-simple-enough/), [Another explanation](http://blog.echen.me/2011/08/22/introduction-to-latent-dirichlet-allocation/)
* [Paper](http://www.jmlr.org/papers/volume3/blei03a/blei03a.pdf)

#####Word2Vec
* [Intuition](http://deeplearning4j.org/word2vec.html), [Making sense of Word2Vec](http://rare-technologies.com/making-sense-of-word2vec/)
* [Paper](https://papers.nips.cc/paper/5021-distributed-representations-of-words-and-phrases-and-their-compositionality.pdf), [Detailed math](http://www-personal.umich.edu/~ronxin/pdf/w2vexp.pdf)

#####Doc2Vec
* [Paper](https://cs.stanford.edu/~quocle/paragraph_vector.pdf)
* [contribution needed: good resources that explain Doc2Vec]

----------

###Advanced Features

#####Query Similarities
* Tool to get the most similar documents for LDA, LSI
* [Similarity queries tutorial](https://radimrehurek.com/gensim/tut3.html)

#####Distributed Computing
* Run LSI and LDA on many computers
* [Distributed computing tutorial](https://radimrehurek.com/gensim/distributed.html)

#####Similarity Server
* Elastic search-like server for document similarity calculated by LSI and LDA
* [Similarity server tutorial](http://radimrehurek.com/gensim/simserver.html)

###[Super Short Feedback Survey](https://docs.google.com/forms/u/0/d/1cyRAlCDYMHb_q5n9II9E_I44P-bzAaEBMTqewy6Vlp8) (Pretty please!)
