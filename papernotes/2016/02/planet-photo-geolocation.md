# PlaNet - Photo Geolocation with Convolutional Neural Networks

* [Arxiv link](http://arxiv.org/pdf/1602.05314v1.pdf)
* [Source code](https://github.com/wulfebw/LittlePlaNet-Models)

### Application
* Infers location based on photos
* Uses multiple photos in an album to dramatically increase accuracy

### Summary
* The current state of the art geolocation detection uses HMMs as an information retrieval problem
* Instead divides Earth into 26,000+ parts, and uses DNNs to solve the classification problem

![earth img](http://s32.postimg.org/kxd8e0oet/Screen_Shot_2016_05_15_at_8_55_10_PM.png)

* Also introduces sequence geolocations with LSTMs, improves accuracy
* E.g. A photo of a wine bar and another of the Eiffel tower in the same album, probably means that the photos are taken in Paris

![album class](http://s32.postimg.org/l2dtjlxn9/Screen_Shot_2016_05_15_at_8_59_12_PM.png)
