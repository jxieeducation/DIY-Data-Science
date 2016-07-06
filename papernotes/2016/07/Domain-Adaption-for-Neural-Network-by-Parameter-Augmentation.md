# Domain Adaptation for Neural Networks by Parameter Augmentation

[Arxiv Link](https://arxiv.org/pdf/1607.00410.pdf)

### Application
* Domain adaption for image captioning, e.g. learning to caption food-specialized photos from a general album
* Another transfer learning methods besides: 1) fine tuning 2) dual output network, with slightly better results

### Summary
* Inspired by a 2007 paper [Frustratingly Easy Domain Adaption](http://www.umiacs.umd.edu/~hal/docs/daume07easyadapt.pdf)
* If the image dataset has X features, then create a network that takes in 3X features, in order to transfer the source domain to the target domain
* <f1, f2, f3>, f1 is the general parameter, f2 is the source domain, f3 is the target domain
* When learning on the source domain, set the parameters to <f1, f2, 0>; when learning the target domain, set the parameters to <f1, 0, f3>
* Tests on the Coco dataset on food vs non-food images and achieves slightly better results compared to 1) fine tuning 2) dual output network
