# Bag of Tricks for Efficient Text Classification

[Arxiv Link](https://arxiv.org/pdf/1607.01759v2.pdf)

### Application
* Showing that text classification with simple n-gram achieves the same state of the art results as RNNs

### Summary
* A simple 2 layer logistic regression
* 1st layer acts as a weight look up, 2nd layer does linear regression, then softmax
* Uses the hashing trick like in VW
* [Reddit comments](https://www.reddit.com/r/MachineLearning/comments/4rp7r0/160701759_bag_of_tricks_for_efficient_text/), [Twitter comment](https://twitter.com/haldaume3/status/751208719145328640)
* vw --ngrams 2 --log_multi [K] --nn 10
