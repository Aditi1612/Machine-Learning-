# Chapter-8: Neural Networks-Representation
## Neural Networks- Overview and summary
### Why do we need neural networks?
+ Logistic regression and linear regression has complexibility and problems handling the complex data.

### Neurons and the brain: 
Our brain has the capability of learning all the process on its own.

Neural networks orginally started as machine that mimics the functions of our brain.

## Model Representation I:
Our neural networks takes one or more input data, processes all the inputted data and outputs the result.

## Artificial neural network - representation of a neurone
+ A neuron is a logistic unit:
>>>> + Feed the input via the input wires.
>>>> + Logistic unit does the computation.
>>>> + Sends the output down the output wires.
 
+ The first layer is called the input layer whereas the last layer is called the output layer.
+ All the layers between the input layer and the output layer is called the hiddens. It is not necessary that a model has a hidden layer (Hidden layer can be even more than one or it can also be none.)

## Neural networks - notation
+  ai^(j) - activation of unit i in layer j :
>>>> + a1^(2) - is the activation of the 1st unit in the second layer.
+ Ɵ^ (j) - matrix of parameters controlling the function mapping from layer j to layer j + 1 :
>>>> + If layer j has Sj units and layer j+1 has Sj+1 units, then the size of theta j is (Sj) X (Sj+1) + 1. (It is added by 1 because of the bias unit.)
+ All the inputs goes to all the nodes in the next layer.

## Model representation II:
Carries out the computation effeciently through a vectorized immplementation and learns the complex non-linear things.

+ Forward propagation: Store,learn and calculates from the order of input layer to output layer.
>>>> + z12 = θ101X0 + θ111X1 + θ121X2 + θ131X3

>>>> + a12 = g(z12)

## Neural Networks learning its own features:
The last node in the neural network is a logistic regression node.

The difference is that the input of the last node is a value calculated from the hidden layer, not the actual input.

## Multiclass classification: 
Multiclass classification is when you distinguish between more than two features.