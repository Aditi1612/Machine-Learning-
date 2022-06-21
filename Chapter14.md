# Chapter-14 : Dimensionality Reduction (PCA)

## Motivation-1: Data Compression
+ Compression: 
>> + Speeds up the algorithm
>> + Reduces the space used by data
>> + Allows us to half the amount of storage
>> + Gives lossy compression, but an acceptable loss.


## Motivation-2: Visualization:
+ Dimensionality reduction can improve how we display the information in a tracable manner for human consumption.


## Principle Component Analysis (PCA) : Problem Formulation
+ For the problem of dimensionality reduction the most commonly used algorithm is PCA.
+ How to determine the line: 
>>> + The distance between each point and the projected version should be small.
>>> + PCA tries to find a lower dimensional surface so the sum of squares onto that surface is minimized.
>>> + PCA tries to find the surface (a straight line in this case) which has the minimum projection error.

+ To reduce from nD to kD we:
>>> + Find k vectors (u(1), u(2), ... u(k)) onto which to project the data to minimize the projection error
>>> + So lots of vectors onto which we project the data
>>> + Find a set of vectors which we project the data onto the linear subspace spanned by that set of vectors

### How does PCA relate to linear regression:
+ PCA is not linear regression.
+ For linear regression, fitting a straight line to minimize the straight line between a point and a squared line.
>>> + NB - VERTICAL distance between point
+ For PCA minimizing the magnitude of the shortest orthogonal distance
+ With linear regression we're trying to predict "y"
+ With PCA there is no "y" - instead we have a list of features and all features are treated equally


## PCA Algorithm: 
Before applying the PCA we must do the mean normalization and feature scaling depending on the data.

With preprocessing done, PCA finds the lower dimensional sub-space which minimizes the sum of the squa

Need to compute two things:
>>> + Compute the u vectors
>>> + Compute the v vectors, z vectors are the new, lower dimensionality feature vectors.

In summary:
+ Preprocessing
+ Calculate sigma (covariance matrix)
+ Calculate eigenvectors with svd
+ Take k vectors from U (Ureduce= U(:,1:k);)
+ Calculate z (z =Ureduce' * x;)


## Reconstruction from Compressed Representation:
Considering 
+ z (vector) = (Ureduce)T * x
To go in the opposite direction we must do
+ xapprox = Ureduce * z
To consider dimensions (and prove this really works)
+ Ureduce = [n x k]
+ z [k * 1]
So,
+ xapprox = [n x 1]


## Advice for applying PCA:
+ Speeding up the supervised learning algorithms: With PCA we can reduce the dimensionality and make it tracable.

+ PCA maps one vector to a lower dimensionality vector
>> + x -> z
>> + Defined by PCA only on the training set
>> + The mapping computes a set of parameters
>>>> + Feature scaling values
>>>> + Ureduce
>>>>>>> + Parameter learned by PCA
>>>>>>> + Should be obtained only by determining PCA on your training set
>> + So we use those learned parameters for our
>>>> + Cross validation data
>>>> + Test set


## Applications of PCA:
+ Compression:
>> + Reduces the memory/disk needed to store the data.
>> + speed up the learning algorithm.
>> + For chosing k ---> % of variance retained

+ Visualization:
>> + Typically choose k=2 or k=3.
>> + A bad use of PCA: Use it to prevent over-fitting .
>> + A second PCA myth
>>>> + Used for compression or visualization - good
>>>> + Sometimes used
>>>>>>> + Design ML system with PCA from the outset.
>>>>>>> + See how a system performs without PCA.
>>>>>>> + PCA is easy to add on as a processing step.
