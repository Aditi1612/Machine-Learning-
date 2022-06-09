# Chapter-10 : Advice for applying Machine Learning

## Debuggging a learning algorithm:

In order to improve the prediction performace or to solve large problems, we can 
+ Increase the training data.
+ Try it with smaller features.
+ Get additional features.
+ Add polynomial features.
+ Create new, better features.
+ Decrease or increase the lambda....
We will choose one of these methods to use. However, this does not always give the desired result.

## Evaluating hypothesis:
Spliting the data into two portions : Training set and the Test set.

## Model selection and training validation test set:
+ Among the polynomials, a model that fits the data should be selected.
+ Calculate the cost function J for each of the function and choose the model that has the smallest error. 
Earlier, we divided the data set into training set 70 : test set 30. 
Now, we will be dividing the data into training set 60: cross validation 20: test set 20.

+ As before, select a model in which the value of the cost function J is minimized in each model and the value of the cost function in cross validation is also small.
Hence, the overfitting problem of the model can be solved.

## Diagonosis - bias vs variance:
+ If you get bad results usually because of one of:
>>> + High bias - under fitting problem
>>> + High variance - over fitting problem

The degree of a model increases as it moves from under-fitting to over-fitting.
If the order is too small, a high bias problem occurs.
+ For the high bias case, we find both cross validation and training error are high:
>>> + Doesn't fit training data well
>>> + Doesn't generalize either
+ For high variance, we find the cross validation error is high but training error is low
>>> + So we suffer from overfitting (training is low, cross validation is high) i.e. training set fits well
>>> + But generalizes poorly

## Regularization and bias/variance:
+ λ = large
>>> + All θ values are heavily penalized
>>> + So most parameters end up being close to zero
>>> + So hypothesis ends up being close to 0
>>> + So high bias -> under fitting data
+ λ = intermediate
>>> + Only this values gives the fitting which is reasonable
+ λ = small
>>> + Lambda = 0
>>> + So we make the regularization term 0
>>> + So high variance -> Get overfitting (minimal regularization means it obviously doesn't do what it's meant to)

## Chosing lamda:
+ Among the models, the model with the smallest value of the cost function J is taken.
+ Check that the value of the cost function of the cross validation set is also small enough
+ Test on the test set.

## Bias/variance as a function of lamda:
+ Jtrain
>>> + When λ is small you get a small value (regularization basically goes to 0)
>>> + When λ is large you get a large vale corresponding to high bias
+ Jcv
>>> + When λ is small we see high variance (Too small a value means we over fit the data)
>>> + When λ is large we end up underfitting, so this is bias (So cross validation error is high)

## Learning curves:
'm' is a constant 
+ Jtrain 
>>> + Error on smaller sample sizes is smaller (as less variance to accommodate)
>>> + So as m grows error grows
+ Jcv 
>>> + Error on cross validation set
>>> + When you have a tiny training set your generalize badly
>>> + But as training set grows your hypothesis generalize better
>>> + So cv error will decrease as m increases

+ High bias (setting straight line to data)
> + Jtrain 
>>> + Training error is small at first and grows
>>> + Training error becomes close to cross validation
>>> + So the performance of the cross validation and training set end up being similar (but very poor)
> + Jcv 
>>> + Straight line fit is similar for a few vs. a lot of data
>>> + So it doesn't generalize any better with lots of data because the function just doesn't fit the data
>>> + No increase in data will help it fit


The problem with high bias is because cross validation and training error are both high
So if an algorithm is already suffering from high bias, more data does not help

+ High variance (high order polynomial)
> + Jtrain 
>>> + When set is small, training error is small too
>>> + As training set sizes increases, value is still small
>>> + But slowly increases (in a near linear fashion)
>>> + Error is still low
> + Jcv 
>>> + Error remains high, even when you have a moderate number of examples
>>> + Because the problem with high variance (overfitting) is your model doesn't generalize