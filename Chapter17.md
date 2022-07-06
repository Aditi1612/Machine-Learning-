# Chapter-17: Large Scale Machine Learning

## Learning with large datasets
The use of Machine learning has developed these days because there are many data these days. Hence, if the data increases, more computation is required.

### Why large datasets?
For high performance is to take a low bias algorithm and train it on a lot of data. But we see that we feed an algorithm with lpts of data they all perform pretty similarly.
<img src="image.png">

### Learning with large datasets
Suppose we want to perform gradient descent with 100,000,000 data.

Then, every time θ is calculated, 100,000,000 calculations are required.

Do we really need to learn with so much data?

If learning is possible with only 1,000 randomly selected data, it is not necessary to use all the data.

This can be verified by drawing a learning curve.

If the graph looks like a high variance problem, then more examples should improve performance,

If the  graph looks like a high bias problem, then more examples may not help.
One natural way to do might be:
>>> + Add extra features
>>> + Add extra hidden units (In neural networks)


## Stochastic Gradient Descent:
Most of the learning derived with an optimization goal (cost function) and  using an algorithm to minimize the cost function.

However, when the data set is large, the computational amount of gradient descent becomes too large, so optimization is carried out in a different way.

The gradient descent we have learned so far is batch gradient descent.


### Stochastic Gradient Descent
This is similar to batch gradient descent, but slightly different.

>>> + random shuffle
>>> + Repeat partial differentiation with respect to theta (no summation)

Instead of calculating the entire dataset, it is sequentially calculated and updated one data at a time.


## Mini batch gradient descent:
Mini batch gradient descent can work even faster than stochastic  gradient descent.

>>> + Batch gradient descent: Use all m examples in each iteration
>>> + Stochastic gradient descent: Use 1 example in each iteration
>>> + Mini-batch gradient descent: Use b examples in each iteration
>>>>>>>>>>+ b = mini-batch size

### Mini batch algorithm:
+ We for-loop through b-size batches of m
+ Compared to batch gradient descent this allows us to get through data in a much more efficient way
>>> + After just b examples we begin to improve our parameters
>>> + Don't have to update parameters after every example, and don't have to wait until you cycled through all the data


## Mini batch gradient descent vs. stochastic gradient descent:

Why should we use mini batch?
+ Have a vectorized implementation.
+ Implementation is much more efficient
+ Can partially paralyze your computation.


## Stochastic gradient descent convergence:

### Checking for convergence:
Unlike batch gradient descent, the stochastic method does not require stopping the algorithm to sum the data.

In stochastic, you can check whether the cost is decreasing well in the middle.


### Learning rate:
There is a way to slowly lower the learning rate as it repeats.

α = constant 1 / (number of repetitions + constant 2)
In this way, the more iterations are made, the smaller the learning rate becomes.

If the learning rate is adjusted in this way, it will reach the global minimum stably.


## Online learning:
Online learning is a model for processing data that is continuously updated.

It is similar to gradient descent in that it updates slowly.

It processes continuously changing data, not fixed data.

And x and y are learned once and discarded. Because new data keeps coming in.


## Map reduce and data parallelism:
+ Spliting the training sets into various different subsets.

You can scale them to a very large data through parallelization.

The advantage of Map Reduce here is that you do not need to worry about the network issues - It is all internal to the same machinere.

Depending on implementation detail, certain numerical linear algebra libraries can automatically parallelize your calculations across multiple coreS.

So, if this is the case and you have a good vectorization implementation you can not worry about local Parallelization and the local libraries sort optimization out for you