# A Convolutional Attention Network for Extreme Summarization of Source Code

* [Arxiv link](http://arxiv.org/pdf/1602.03001v1.pdf)
* [Source code](https://github.com/mast-group/convolutional-attention/)
* [Data set](http://groups.inf.ed.ac.uk/cup/codeattention/)

### Application
* This conv + attention network learns to summarise source code functions
* Given a sequence of words from the source code, outputs a sequence for the suggested method name

![source code summarisation](http://s32.postimg.org/q0ns2v39x/Screen_Shot_2016_05_09_at_10_12_25_PM.png)

### Summary
* 1D convolution of source code tokens feeds into 2 layers of stacked attention network
* Also incorporates a copy framework to suggest out of vocabulary tokens
* Weighed sum of the attention tokens is decoded via GRUs and hybrid beam and BFS
* Data is collected from 10MB of Java repos on Github

![net architecture](http://s32.postimg.org/rc2fdy0yd/Screen_Shot_2016_05_09_at_10_18_36_PM.png)

![attention visualization](http://s32.postimg.org/cu1juyi51/Screen_Shot_2016_05_09_at_10_21_14_PM.png)
(Attention visualization for getNode())

