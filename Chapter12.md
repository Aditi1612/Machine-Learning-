# Chapter-12 : Support Vector Machines

## Support Vector Machine(SVM) - Optimizatiom objective:
Compared to both logistic regression and neural networks, a SVM ( ansupervised learning algorithms) sometimes gives a cleaner way of learning non-linear functions

## An alternative view of logistic regression:
As before, the hypothesis function of logistic regression is as follows. $$ h_{\theta}(x) = \frac{1}{1 + e^{-{\theta}Tx}} $$ . This function is called the hinge loss function.

## Kernels - I: Adapting SVM to non-linear classifiers:
What are kernels and how do we use them?
=> Comes up with a omplex set of polynomial features to fit the data. Have hθ(x) which returns 1 if the combined weighted sum of vectors (weighted by the parameter vector) is less than or equal to 0, else return 0

### What does sigma do?
+ σ2 is a parameter of the Gaussian kernel
+ Defines the steepness of the rise around the landmark


## Kernels- II:
### Choosing tthe landmarks:
+ Take the training data
+ For each example place a landmark at exactly the same location
+ So end up with m landmarks
>>> + One landmark per location per training example
>>> + Means our features measure how close to a training set example something is

### SVM training with kernels:
+ Now we use f instead of x as the feature vector to minimize it.
+ By solving this minimization problem, we can get the parameters for the SVM.
+ The kernel can be applied to other algorithms as well.
However, SVM is much more efficient than other algorithms.

### SVM hypothesis prediction with kernels
+ Predict y = 1 if (θT f) >= 0
+ Because θ = [m+1 x 1]  And f = [m +1 x 1]

### SVM parameters (C):
+ Bias and variance trade off
+ Must chose C
+ Large C gives a hypothesis of low bias high variance --> overfitting
+ Small C gives a hypothesis of high bias low variance --> underfitting
+ Given a new example, compute all the f values

### SVM parameters (σ2)
+ Parameter for calculating f values
>>> + Large σ2 - f features vary more smoothly - higher bias, lower variance
>>> + Small σ2 - f features vary abruptly - low bias, high variance


## SVM - implementation and use:
Use SVM software packages (e.g. liblinear, libsvm) to solve parameters θ
Need to specify
+ Choice of parameter C
+ Choice of kernel

Choosing of kernel:
+ Gaussian kernel:
>>> + Need to define σ (σ2)
>>> + When to choose: if n is small or/and m is large.
>>> + If you are using a Gaussian kernel then you need to implement the kernel function.
>>> + If the values of the features differ a lot in size, they make the values similar through preprocessing.

+ linear kernel: 
>>> + It is used when the kernel is not available. (Therefore, there is no f vector.)
>>> + It is mainly used when n is large and m is small.


## Multi-class classification for SVM:
+ Many packages have built in multi-class classification packages
+ Otherwise use one-vs all method
 
## Logistic regression vs SVM:
Whether to use Logistic Regression or SVM is decided through n (features) and m (training set).

+ If n is greater than m
>>> + logistic regression or SVM
+ If n is small and m is medium
>>> + Gaussian kernel is good.
+ If n is small and m is large
>>> + Because Gaussian kernel is slow, linear kernel SVM and logistic regression are used.