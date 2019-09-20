# Keras vs SciKitLearn vs Pytorch

The idea of these notebooks is to compare the the performace of Keras (Tensorflow backend), PyTorch and SciKitLearn on the MNIST image classification problem.

The following parameters were set up equally in the three frameworks:
- Architecture of the neural network
 
Two hidden layers, each with 100 neurons and relu activation functions.
One softmax layer as output

- Loss function

Cross entropy loss

- Initialisation of the weigths

Glorot initialisation


- Optmiser

Adam with the default parameters

- Data 

The MNIST dataset is loaded from keras (70000 images). The data is split into a training (60000 images) and a test set (10000 images). 

- Fit

The fitting process is done using minibatches of 500 images for a total of 100 epochs.


## PyTorch

The function categorical cross entropy is not implemented in PyTorch for the calculation of the loss. We implement our own function to calculate it based on https://datascience.stackexchange.com/questions/55962/pytorch-doing-a-cross-entropy-loss-when-the-predictions-already-have-probabiliti


## SciKitLearn

It is not possible to manually choose the type of activation used for the output layer. In order to have a softmax layer as output, the type of the output has to be "multiclass". This means that the "y target" values should not be input as one-hot vectors.

 
SciKitLearn only supports fully connected layers for the neural networks, we also do not use any type of convolutions on Keras or PyTorch
