# Not Just a Black Box: Learning Important Features Through Propagating Activation Differences

[Arxiv link](http://arxiv.org/pdf/1605.01713v1.pdf)

### Application
* NNs are basically blackboxes, which means little interpretability
* DeepLIFT assigns importance scores for the input features

### Summary
* DeepLIFT - Learning Feature Importance
* A neuron's activation is its activation under reference input
* Defines a concept of "contribution" that can be calculated one step at a time, like backprop
	* For instance, C (x to t) = SUM C (x to y) * C (y to t)
	* The paper goes on to describe how the "backprop" of C is calculated for functions like maxpool, max
* Shows examples of DeepLIFT on ImageNet...etc.

![deeplift demo](http://s32.postimg.org/o9galuamd/Screen_Shot_2016_05_07_at_10_12_32_PM.png)
