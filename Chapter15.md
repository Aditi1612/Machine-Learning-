# Chapter-15: Anamaly Detection

## Anomaly detection- problem motivation
+ Anomaly detection can be thought of as a solution to an unsupervised leaning problem,
+ An anomaly detection method is used to see if the new engine is anamalous.


# How do we do this?
+ First, using our training dataset we build a model 
>>>> + We can access this model using p(x)
>>>> + It tells "What is the probability that example x is normal" 
+ Having built a model
>>>> + if p(xtest) < ε --> flag this as an anomaly
>>>> + if p(xtest) >= ε --> this is OK
>>>> + ε is some threshold probability value which we define, depending on how sure we need/want to be


## Applications:
+ Fraud detection
+ Manfucturing
+ Monitoring computers in data center


## The Gaussian distribution:
It is also called the normal distribution.
~ N(μ,σ2 ) where mu is the mean and sigma is the standar deviation specifying the width of the Gaussian probability.

Gaussian equation is
P(x : μ , σ2) (probability of x, parameterized by the mean and squared variance).

## Anamaly detection algorithm:
We have a training set for x data.

x will have a unique distribution for each n features.

Find μ and σ2 for each feature.

Multiplying the Gaussian distribution of all features gives p(x).
+ p(x) = p(x1; μ1, σ12) * p(x2; μ2, σ22) * ... * p(xn; μn, σn2)


### Algorithm:
+ Choose the features that describes the general properties.
+ Fit the parameters 
>>>> + Determine the parameters for μi and σi2
>>>> + Used some vectorized implpementation rather than a for loop.
+ Compute p(x)
>>>> + Compute the formula for the Gaussian probability
>>>> + If the number is very small then it is not normal.


## Developing and evaluating amd anomaly detection system:
So far, we have seen the method if evaluating machine learning algorithm by returning a real number and it can be easily evaluated if it returns a single number in order to show if changes you have made have impoved or worsened the performance.

The anomaly data examined so far were unlabeled data. If this becomes labled data, it will be possible to evaluate it.

So, if the specific data is anomaly data, it is defined as y = 1, otherwise, if it is normal data, the label is created with y = 0.


### Airplane engine example:


Let's take an airplane engine as an example.

There are 10000 normal engines and there are 20 abnormal engines.

training set: 6000 normal engines
cv set: 2000 normal engines and 10 abnormal engines
test set: 2000 normal engines and 10 abnormal engines
The ratio is about 3:1:1. The cv set and test set must use different data.

Consider an algorithm that predicts such an anomalous engine.

We label our data, so it looks like supervised learning.

As we have a lot of data for y=0, so we should not calculate the perfomance of the algorithm in the ususal way.

1. Calculate the true positive, false positive, true negative and the false negative.
2. Calculate the precision and recall.
3. Calculate the F1 score.



## Anomaly detection vs. supervised learning:

Aomaly detection:
+ Very small number of positive examples.
+ Very large number of negative examples.
+ Many types of anomalies: Hard for an algorithm to learn from positive examples when anomalies may look nothing like one another.
+ Applications:
>>> + Fraud detection
>>> + Manufacturing 
>>> + Monitoring machines in data.


Supervised learning:
+ Reasonably large number of positive and negative examples.
+ Applications :
>>> + Email/Spam classification
>>> + Weather prediction
>>> + Cancer classification


## Choosing features to use:

+  For non-gaussian feautures, use different types of transformations of the data to make it look like more Gaussian.

### Error analysis for anomaly detection:
Similar to supervised learning, you perform algorithms using cv sets.

The result is that it analyzes the wrong thing and creates a new feature that can be corrected.

The best case is that p(x) of normal data is large and p(x) of abnormal data is small.

However, in a real-world situation, p(x) of normal and abnormal data may exist in a similar range.

In this case, we draw out cases where the data is anormal but where p(x) is large, and we analyze it and devise a new feature to distinguish them.


## Multivariate Gaussian distribution:
+ Is a slightly different technique which can sometimes catch some anomalies which non-multivariate Gaussian distribution anomaly detection fails to.

###  Multivariate Gaussian distribution model:
The Multivariate Gaussian distribution, unlike the Gaussian distribution so far, models p(x) at once instead of using each feature individually.

parameter

μ - n-dimensional vector
Σ - Matrix of size [nXn] (covariance matrix)


## Original model vs. multivariate Gaussian:

Original Gaussian model: 
+ Used more often
+ There is a need to manually create features to capture anomalies where x1 and x2 take unusual combinations of values.
>>> + Need extra features.
+ Cheaper computation
+ Works well even with a small training set
+ Scales much better to very large feature vectors.


Multivariate Gaussian model:
+ Used less frequently
+ Can capture feature correlation 
+ Less computation efficient 