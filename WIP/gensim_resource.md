

Text to Vector
https://radimrehurek.com/gensim/tut1.html
Corpus:


--------------

models:
[quality of life]
- phrase
- tfidf
[topic modeling]
- lda
- lsi
- rp
- hdp

TFIDF:
https://github.com/piskvorky/gensim/blob/develop/gensim/models/tfidfmodel.py
https://radimrehurek.com/gensim/models/tfidfmodel.html
http://stackoverflow.com/questions/9470479/how-is-tf-idf-implemented-in-gensim-tool-in-python
term `i` in document `j` in a corpus of D documents:
    weight_{i,j} = frequency_{i,j} * log_2(D / document_freq_{i})
http://michaelerasm.us/tf-idf-in-10-minutes/

Phrases:
https://github.com/piskvorky/gensim/blob/develop/gensim/models/phrases.py
https://radimrehurek.com/gensim/models/phrases.html
**can be used in Word2Vec
http://www.markhneedham.com/blog/2015/02/12/pythongensim-creating-bigrams-over-how-i-met-your-mother-transcripts/
http://datascience.stackexchange.com/questions/6052/how-to-recognize-a-two-part-term-when-the-space-is-removed-bigdata-and-big


------

Word2vec:
https://github.com/piskvorky/gensim/blob/develop/gensim/models/word2vec.py
https://radimrehurek.com/gensim/models/word2vec.html
https://codesachin.wordpress.com/2015/10/09/generating-a-word2vec-model-from-a-block-of-text-using-gensim-python/
expain:
http://arxiv.org/pdf/1402.3722v1.pdf
http://rare-technologies.com/making-sense-of-word2vec/
http://deeplearning4j.org/word2vec.html
http://www-personal.umich.edu/~ronxin/pdf/w2vexp.pdf


Doc2vec:
https://github.com/piskvorky/gensim/blob/develop/gensim/models/doc2vec.py
https://radimrehurek.com/gensim/models/doc2vec.html
http://arxiv.org/pdf/1405.4053v2.pdf
** Can't plug in normal corpus
https://linanqiu.github.io/2015/10/07/word2vec-sentiment/
http://stackoverflow.com/questions/31321209/doc2vec-how-to-get-document-vectors


random projection:
https://github.com/piskvorky/gensim/blob/develop/gensim/models/rpmodel.py
https://radimrehurek.com/gensim/models/rpmodel.html
http://fastml.com/dimensionality-reduction-for-sparse-binary-data/
http://users.ics.aalto.fi/ella/publications/randproj_kdd.pdf

LDA:
https://github.com/piskvorky/gensim/blob/develop/gensim/models/ldamodel.py
https://radimrehurek.com/gensim/models/ldamodel.html
tedunderwood.com/2012/04/07/topic-modeling-made-just-simple-enough/
https://rstudio-pubs-static.s3.amazonaws.com/79360_850b2a69980c4488b1db95987a24867a.html
http://brandonrose.org/clustering#Latent-Dirichlet-Allocation
http://confusedlanguagetech.blogspot.in/2012/07/jordan-boyd-graber-and-philip-resnik.html

LSI:
https://github.com/piskvorky/gensim/blob/develop/gensim/models/lsimodel.py
https://radimrehurek.com/gensim/models/lsimodel.html
PCA on term-document matrix
https://www.researchgate.net/post/LSA_SVD_How_to_statistically_interpret_negative_values_in_U_and_Vt


