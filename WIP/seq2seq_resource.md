
paper:

main

http://arxiv.org/pdf/1406.1078.pdf
cho et al. Eng - French translation
Introduces encoder-decoder framework (good graph on page 2)
2 use cases: 1. seq to seq 2. score target sequence prob
2–D embedding of the learned phrase representation
the performance of a basic encoder–decoder deteriorates rapidly as the length of an input sentence increases
make note of greedy vs beam search in prediction


http://arxiv.org/abs/1409.3215
- it helps to reverse the input sequence, LSTM learns much better when the source sentences are reversed
- backpropagation has an easier time “establishing communication” between the source sentence and the target sentence



http://arxiv.org/pdf/1409.0473v6.pdf
introduces attention framework!!
propose that the fixed length embedding is the bottleneck 
it does not attempt to encode a whole input sentence into a single fixed-length vector.
Instead, it encodes the input sentence into a sequence of vectors and chooses a subset of these vectors adaptively while decoding the translation.
The new architecture consists of a bidirectional RNN as an encoder (Sec. 3.2) and a decoder that emulates searching through a source sentence during decoding a translation
Encoder (bidirectional) creates an annotation of a word (forward + backward). Annotations are a representation of what role a input word plays in the input sentence. 
In decoding, the next word in the sequence is a function of (y_i-1, i_t, c_i). c_i is a linear combination of annotations.
Good demo on page 7

http://arxiv.org/pdf/1506.05869v1.pdf
models IT helpdesk, OpenSubtitles dataset
n-gram models improve performance
good examples for demo


less main

http://arxiv.org/pdf/1511.06391.pdf
- handles inputting sets (like a set of numbers to sort them)
- input sets: swapping two elements xi and xj in the set X
	- uses attention mechanism instead
	- READ - Process - Write
	- process encodes input to memory that is invariant to order of inputs, attention mechanism
	- write block - LSTM pointer network
- output sets: find optimal way to order the set via combinatorics

http://arxiv.org/pdf/1603.06393.pdf
- copying, in which certain segments in the input sequence are selectively replicated in the output sequence --> CopyNET
- COPYNET can nicely integrate the regular way of word generation in the decoder with the new copying mechanism which can choose subsequences in the input sequence and put them at proper places in the output sequence
- related to rote memorization
- combines attention with copying, linear addition of probability
Prob(“Jebara”) = Prob(“Jebara”, g) + Prob(“Jebara”, c)

https://www.aclweb.org/anthology/P/P15/P15-1152.pdf
- Built a single-conversation (1 post to 1 reply) training dataset off of Weibo (chinese twitter)'s
- Used separate embeddings for post and reply, because words had different distributions
- Defines attention based decoding as NRM-local and non-attention based decoding as NRM-global (sec 3.2) (not related to Effective Approaches...)
- Creates a hybrid model by combing NRM-local and -global, which naively concats the context vectors (sec 3.3)

http://stanford.edu/~lmthang/data/papers/emnlp15_attn.pdf
- Focuses on improving the attention mechanism proposed from [the attention paper above]
- Defines a global attention model that is a simplified derivation from the paper
- Defines a local attention model that focuses only on a small subset of the source positions per target word to reduce computation for long inputs


http://www.cinjon.com/papers-multimodal-seq2seq/
http://arxiv.org/pdf/1511.01432v1.pdf 
- can use Seq2Seq autoencoder as a pre-training step to improve stability in training tasks with LSTM such as document classification

http://arxiv.org/pdf/1511.06114v1.pdf
- Trains the same encoder and decoder on many different tasks at the same time
- Can be done as one (encoder) to many (decoder), many to one and many to many for tasks like image captioning and machine translation
- Trains different tasks at the same time, each N minibatches at a time 


blog: 
http://domkaukinen.com/tag/seq2seq/
https://indico.io/blog/sequence-modeling-neuralnets-part1/


projects:
 
TF - https://github.com/inikdom/neural-chatbot
Torch - https://github.com/macournoyer/neuralconvo
Torch - https://github.com/harvardnlp/seq2seq-attn
Keras - https://github.com/nicolas-ivanov/debug_seq2seq
Chainer - https://github.com/kenkov/seq2seq
Theano - https://github.com/adamchanson/seq2seq
TF - https://github.com/nicolas-ivanov/tf_seq2seq_chatbot
Torch - https://github.com/eriche2016/seq2seq-1
Raw numpy - https://github.com/ma2rten/seq2seq


data sets:
WMT '14' eng-french

