# LSTM-based Encoder-Decoder for Multi-sensor Anomaly Detection

[Arxiv Link](https://arxiv.org/pdf/1607.00148.pdf)

### Application
* A novel way to do time series anomaly detection

### Summary
* Inspired by the recent seq2seq advancements, perform anomaly detection via encoding and decoding the time series
* Act like an autoencoder, where a high reconstruction error correspond to a likely anomaly
* Just like Sutskever et al., 2014, reverses the input sequence as the y
* Produces the anomaly score by scaling the error for the multivariate data by the precision matrix (inverse covariance matrix)
![formula for anomaly score](https://s31.postimg.org/yit4omi2j/Screen_Shot_2016_07_05_at_6_23_52_PM.png)
* Divides the time series dataset into multiple sets, 1 set for training, 1 set for validation, 1 set for determining the threshold for anomaly and 1 set for testing
