# Vote-Boosting Ensembles

[Arxiv Link](https://arxiv.org/pdf/1606.09458v1.pdf)

### Application
* A novel vote based boosting technique that has comparable or slightly better performances than adaboost
* Generalizes well to outliars and avoids tunneling on noise in data

### Summary
* In the boosting process, instead of focusing on false predictions, focus on disagreements among the predictions of classifiers in the ensemble
* Giving excess weight to false predictions (typically noise or outliar) tends to lead to a deterioration of the generalization performance
* Instead try to focus on training examples with the most disagrement (half of the classifiers say yes, others say no)
* Weight the training examples using a beta distribution: the more disagreement, the more weight
* Sample the dataset according to the weights, so higher weighted samples are more likely to be chosen
* Demonstrates the power of vote-boosting by noising 2 popular datasets, where adagrad focuses on fitting the noise, whie v-b ignored the noise
