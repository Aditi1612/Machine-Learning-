# Chapter-11 : Machine Learning System Design

## Prioritizing what to work on - spam classification example:
+ Distinguishing between spam and not spam:
>>> + Spam (1): Mispelled word
>>> + Not Spam (0): Real Content

## One approach - chosing your own features: 
+ Chose 100 words which are indicative of an email being spam or not spam
>>> + Spam --> e.g. buy, discount, deal
>>> + Non spam --> Andrew, now
>>> + All these words go into one long vector
+ Encode this into a reference vector
>>> + See which words appear in a message
+ Define a feature vector x
>>> + Which is 0 or 1 if a word corresponding word in the reference vector is present or not
i.e. don't recount if a word appears more than once

## What is the best use of your time to improve system accuracy?
+ Natural inclination is to collect lots of data.
+ Develop sophisticated features based on email routinf information. 
+ Develop sophisticated features for message body analysis 
+ Develop sophisticated algorithm to detect mispelling

## Error analysis: 

It is a good idea to start by building a simple algorithm that can be implemented quickly.

+ Test with cross validation data.
+ Draw a learning curve to determine whether increasing data or increasing features will help.
+ Analyze the data that is causing the error and observe what kind of data is causing the error.

>> + error analysis: 
>>>> + Manually examines the samples that your algorithm made errors on.
>>>> + Find the most common types.
>>>> + Classify them correctly and find which features would have helped.

Importance of numerical evalution: It gives a single real number and tells how well the algorithm is doing.
Although a single value is hard or complicated to compute but it makes it much easier to evaluate how changes impact your algorithm.

## Error metrics for skewed analysis:
When the data to be classified is much smaller than the unclassified data, these data are called skewed classes.

When classifying skewed classes, errors are checked in a different way, not in a general way.

Two new matrices - precision and recall.
True positive (we guessed 1, it was 1)
False positive (we guessed 1, it was 0)
True negative (we guessed 0, it was 0)
False negative (we guessed 0, it was 1)

## Precision: 
How often does our algorithm cause a false alarm?
+ = true positives / # predicted positive
+ = true positives / (true positive + false positive)
High precision is good (i.e. closer to 1)
+ You want a big number, because you want false positive to be as close to 0 as possible.

## Recall: 
How sensitive is our algorithm?
+ = true positives / # actual positives
+  = true positive / (true positive + false negative)
High recall is good (i.e. closer to 1)
+ You want a big number, because you want false negative to be as close to 0 as possible

## Trading of precision and recall:
Previously we have trained a logistic regression classifier as 1 if the threshold was greater than 0.5 otherwise 0.

If this value is increased like 0.7 or 0.8, the accuracy for cancer patients increases, but the degree of misjudgment of cancer patients as normal people increases.That is, it appears as high precision and lower recall.
That is, it appears as high precision and lower recall.

Conversely, if the threshold value is set small, the cases of high recall, lower precision, and misjudgment of cancer patients are reduced, but the cases of judging normal people as cancer patients also increase, resulting in lower accuracy.

In order to solve these problems, we have to choose the optimal algorithm that is more convinient to comnbine the two numbers that evaluate the performance.
Hence, the F-score is generally used.

Threshold offers a way to control trade-off between precision and recall

Fscore gives a single real number evaluation metric

## Data for machine learning:
At times, adding more data can be considered as an effective way to improve the performance.

### Designing a high accuracy learning system:
It is concluded that:
+ Algorithms give remarkably similar performance
+ As training set sizes increases accuracy increases
+ Take an algorithm, give it more data, should beat a "better" one with less data

When it is true and when it is not/
+ If we correctly assume that features x have enough information to predict y accurately, then more data will probably help.
+ Assuming of using a learning algorithm with many parameters such as logistic regression or linear regression with many features, or neural networks with many hidden features:
>>> + Such algorithms are low bias algorithms.
>>> + Use a small training set.
>>> + Use a large training set. (If the training set error is close to the test set error.)


Low bias --> use complex algorithm

Low variance --> use large training se