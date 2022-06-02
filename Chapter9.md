# Chapter-9: Neural Networks - Learning

## Neural network cost function: 
Neural network, an algorithm for fitting parameters derived from a training set. 
Let L be the number of layers in the network and S1 be the number of units in layer 1.

## Types of classification problems with Neural Networks:
+  Binary  Classification: The output is 0 or 1. As there is only one ooutput node, then Sl =1.
+ Multi-class classification: It is classified into k numbers that can be 3 or more output nodes. Hence, Sl=k.

## Cost function for neural networks: 
For neural networks the cost function is a generalization of the logistic cost function,  but instead of outputting one, we generate k outputs.

## Summary of whats about to go down: 
+ Back Propagarion: 
>>> + Method to calculate the output value of a neural network with the actual value and calculating how many incorrect values the parameters have.
>>> + Using the error calculated with the use of output value, the error of the parameters in the previous layer is calculated. It is repeated until the input layer is reached.
>>> + The error is calculated using the partial derivatives.
>>> + Gradient descent and partial derivatives are used together to minimize the cost function and update all parameters. The gradient descent method is repeated until the values ​​converge.

## Back propagation algorithm: 
Using the partial derivatives to minimise the cost function.

## What is back propagation?
δjl represents the error of the j node in the l layer.

Since the value of the activation node is already calculated, the value of the error is also a real number.

The calculation starts from the values ​​in the output layer.

## Back propagation algorithm: 
If you find the value of a parameter through partial differentiation, we cannot update the values immediately. Since the calculated value is continuously used, if you update it in advance, the value comes out strangely a it reaches the input node.
You need to find the values ​​of all parameters and then update them at the same time.