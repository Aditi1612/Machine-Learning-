# Chapter-13 : Clustering 

## Unsupervised learning - introduction:
Comparing and contrasting supervised learning and unsupervised learning:

+ Supervised learning
>>> + Given a set of labels, fit a hypothesis to it
+ Unsupervised learning
>>> + Try and determining structure in the data
>>> + Clustering algorithm groups data together based on data features

Clustering is good for:
+ Market segmentation
+ Social network analysis
+ Organizing computer clusters
+ Astronomical data analysis


## K-means algorithm: 
### Overview:
+ Take unlabeled data and group into two clusters:

### Steps:
+ Randomly allocate two points as the cluster centroids
+ Cluster assignment step
+ Move centroid step
>>> + Take each centroid and move to the average of the correspondingly assigned data-points 
+ Repeat 2) and 3) until convergence

### K-means for non-separated clusters:
+ Often K-means is applied to datasets where there aren't well defined clusters  (e.g. T-shirt sizing) 
+ For example, if you want to divide the above T-shirt size data into three sizes (S, M, L), you can apply k-means clustering to the data.
Therefore, it can be divided into three groups.


## K-means optimization objective:
+ In k-means clustering, it has an optimization objective just like the supervised learning.
+ The objective of k-means clustering:
>>> + ci is the index of clusters {1,2, ..., K} to which xi is currently assigned
>>> + μk, is the cluster associated with centroid k
>>> +  μci, is the cluster centroid of the cluster to which example xi has been assigned to

In other words, the goal is to minimize the square of the distance between the data and the center point.
The cost functin is also called disstortion in CLustering.

### k-means algorithm:
+ The cluster assigned step is minimizing J(...) with respect to c1,c2,..,ci
+ The move centroid step
+ Hence, we are partitioning the algoruthm into two parts:
>>> + First part minimizes the c variables.
>>> + Second part minimizes the J variables.
+ We can use this knowledge to debug our K-means algorithm.

### Random initialization:
How to initialize the center point
+ Set the center point of a number smaller than the number of data m. (If k > m, there is a problem)
+ k may converge to different solutions depending on the initialization point.
>>> + There is a risk of a local optimum
 
In order to solve the convergence to the local optimum
+ After random initialization several times, check the result.
+ If there are many identical results, it is highly likely to indicate a global optimum.


## How do we choose the number of clusters?
+ Choosing K?
>>>+ Not a great way to do this automatically
>>>+ Normally use visualizations to do it manually
+ Why is this hard
>>>+ Sometimes very ambiguous
>>>+ e.g. two clusters or four clusters
>>>+ Not necessarily a correct answer
>>>+ This is why doing it automatic this is hard

### Elbow method: 
+ There is a way to choose the most appropriate value of k.
When the cost function J is drawn according to the number of k, if there is an elbow point where the cost hardly changes after a certain k, it would be reasonable to select that k. 

+ However, this method does not always work. If the change of J is generally smooth as follows, there is no point that can be called elbow. 


## Another method for choosing K: 
Another way is to make adjustments for the purposes we want to know.

In the case of an example of classifying the size of a T-shirt, it can be adjusted to suit the purpose by dividing it into three or five.