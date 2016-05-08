- Ask Your Neurons: A Neural-based Approach to Answering Questions about Images
- http://arxiv.org/pdf/1505.01121.pdf
- uses a single LSTM network, responsible for both encoding and decoding the question and answer
- input is the raw concatenation of the word embedding of a word with the representation from the last layer of ImageNet
- tested on DAQUAR, measure using accuracy and WUPS
- WUPS is like accuracy, but also accounts into similar words (e.g. cat, kitty)
- introduced the idea of a blind model, so no looking at the picture
- Surprisingly, the blind model produces only slightly worse accuracy than with the CNN input. Meaning that the questions are biased and not diverse enough
- Doubles none deep learning results


- Are You Talking to a Machine?
- http://arxiv.org/pdf/1505.05612.pdf
- very different architecture
- CNN image representation
- one LSTM to create sentence embedding
- one LSTM to create embedding for answer
- A fusing component that takes inputs from all 3 previous pieces to generate the next word in the answer
- tested on the MS Coco dataset 
- Also employed humans to evaluate quality of answers
- Humans 95%, blind QA 34%, mQA 65%


- Exploring Models and Data for Image Question Answering
- http://arxiv.org/pdf/1505.02074.pdf
- Made a breakthrough in greatly enhancing the number of training examples (more than 20x)
- Generates training examples from image captions, through using the Stanford parser to extract relationships within the image
- Unlike other LSTM nets, inputs CNN representations as the first input for the LSTM (other nets combines the CNN representations with every word embedding in question)
- Performs softmax on the LSTM output of the last sentence input
- In section 4.2 and 4.3 introduces many baseline net architectures


- Image Question Answering using Convolutional Neural Network
with Dynamic Parameter Prediction
- http://arxiv.org/pdf/1511.05756.pdf
- This is a very creative paper that is different from others
- Solves only for single answer question, to reduce the main network to solve for a classification problem
- Other architectures have LSTM as the main framework, this paper uses the convnet / regular DNN as the main piece
- Question is embedded via GRUs to dynamically control the weights of the second last layer of the CNN / DNN, which is very original
- To predict a large number of weights in the dynamic parameter layer effectively and efficiently, applies hashing trick, which reduces the number of parameters significantly with little impact on network capacity
- Shows that the hashing trick does not drastically deteriorate the accuracy of the classification network
- tests on DAQUAR, COCO and VQA
- about 10% more accuracy compared to the Ask Your Neurons network (19%)


- Stacked Attention Networks for Image Question Answering
- http://arxiv.org/pdf/1511.02274v2.pdf
- Not all parts of the image are relevant to the QA
- Introduces the use of attention layers to select which part of the CNN representation should be passed on
- Most other CNN models use the last fully connected layer in CNN
- This paper takes features from the last pooling layer
- The image is divided into 14x14 sections, and each section has 512 features from the filters
- The LSTM question embeddings and the CNN representations are passed into a stacked attention network 
- Note: use stacked attention network instead of a single attention network to learn complicated relationships 
- The output is a softmax layer that figures out which section of the image is important, which is linearly combined as input to a fully connected classification net
- 12% higher accuracy than Ask Your Neuron


- VQA: Visual Question Answering
- http://arxiv.org/pdf/1505.00468.pdf
- 








- DAQUAR-ALL
- what is on the left side of the white oven on the floor and on right side of the blue armchair in the image1 ?
garbage_bin
- http://www.mpi-inf.mpg.de/departments/computer-vision-and-multimodal-computing/research/vision-and-language/visual-turing-challenge/


- DAQUAR-REDUCED
- COCO-QA
- VQA


