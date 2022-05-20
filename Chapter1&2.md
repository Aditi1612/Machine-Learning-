
# Chapter-1&2: Introduction to Machine Learning, Regression Analysis and Gradient Descent
### Contents:
+ Supervised Learning
+ Unsupervised Learning
+ Linear Regression and its Implementation (Cost Function)
+ Gradient Descent



Machine Learning: " A computer program is said to learn from Experience E with respect to some class of tasks T and performance measure P, if its performanc at tasks in T, as measured by P, improves with experience E."
There are several types of algorithm:
+ Supervised Learning:
>>>> + Regression Problem
>>>> + Classification Problem
+ Unsupervised Learning:
>>>> + Clustering 
>>>> + Non-clustering 


## Supervised Learning: 
In Supervised Learning, we roughly have an idea how the output will look like. In this we gave an algorithm a data set where a "right answer" was provided. Supervised Learning is categorised into : 1) Regression Problem and 2) Classification Problem

Regression problem is used to predict the output where the output is in continuous i.e mapping  the input variables to some contiuous output value. Example: the prcie of the house (It can have a real values) 
Whereas, in classification prblem, it predicts the output where the output is in discrete value.Example: Given a patient having covid-19, we have to predict whether the disease is symptomatic or asymtomatic.


## Unsupervised Learning:
In Unsupervised Learning, we dont have any idea how the output will look like. We have to derive a data set ny clustering the data based on the similarities among the variables in the data. Also, we do not have any feedabck based on the prediction results.

Example of clustering: A gene of different types, finding a way to group these genes that have similar feature related to each other in the given data.

Expample of non-clustering: The " Cocktail Party Algorithm" allows to find a suituable structure even in a chaotic environment.

## Linear Regression and its Implementation (Cost Function): 
When given a training set, pass a learning algorithm and then the algorithm outputs the estimated value of "Y".

### Cost Function: 
The cost function helps us to obtain the best straight line that can be fitted in the given data. A way to determine the values for the theta values which makes the hypothesis ( to make s accurate as posssible)
It is considered as the value obtained by subtracting the result value guessed by the algorithm from the calculated result value.
Our main goal is to minimize the cost function (J).

## Gradient Descent: 
An algorithm to minimize the cost function (J). It is such a method that is used everywhere in machine learning for minimization.
The steps are:
>>+ Take an initail guess of the values:
>>>>>> + It is preferred to start at (0,0) or you can use any other values.
>>>>>> + Keep changing the values slightly and reduce the cost function.
>>+ Choose the gradient which reduces the maximum cost function.
>>+ Repeat until you reach converge to a local minimum.(It is said that there can be more than one local minimum depending on the intialization point you took.)
>>>>>> + At each iteration j, one should be simultaneously the parameters. Updating a specific parameter prior to calculating another one on the jth iteration will result in a wrong implementation.

We should ajdust the parameter alpha (learning rate) to ensure that the gradient descent algorithm converges in a reasonable time. If we fail to converge or is taking too much time to converge the minimum value, then it can be concluded that our step size is wrong.
>>>> +  If the learning rate is too small, then the gardient descent can be slow.
>>>> + If the learning rate is too large, then the gradient descent can overshoot the minimum. It will to converge or can even diverge
>>>> + The gradient descent can converge to a local minimum, even when the learning rate is fixed: As we approach a local minimum, gradient descent will automatically take smaller steps. Hence, we do not need to decrease the learning rate with  time.

### Local Minimum VS Global Minimum:
Local minimum are called so since the value of the loss function is minimum at that point in a local region. Whereas, a global minima is called so since the value of the loss function is minimum there, globally across the entire domain the loss function.



