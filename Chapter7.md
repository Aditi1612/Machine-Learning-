# Chapter-7: Regularization

## The problem of overfitting:
Overfitting occurs when we train the model with a lot of data or features, making the hypothesis function too complpex. A model whose hypothesis function is overfitted then the prediction of the result is very difficult. Hence, we cannot gurantee of thr correct result to be outputted. 
<br>
The problem of not being able to express a general trend because it is too fitted to the training data is called overfitting.

#### Adressing the overfitting problem:
1) Reducing the number of features:
>>> + Manually selecting which feature to keep and which not to.
>>> + But, in reducing the number of features we can lose some useful information.

2) Regularization:
>>> + Keeping all the features, but reducing the magnitude of the parameter theta.
>>> + Works well when we have a lot of features, each of which contributes a bit to predict y.

## Cost function optimizarion for regularization:
+ Keeping all the features but reducing the size of the parameter theta small.
>>> + Useful when many features contribute a little to predicting y.
+ Adding lamda that is the regularization constant.
>>> + If the lamda is set to very large then all the theta parameters become 0 and hence only the theta0 remains, which becomes a function of underfit.
>>> + It is very important to set the appropriate value for theta in order to avoid the problem of underfit.
+ Theta0 is a constant value, hence it is not included in the regularization

## Regularization linear regression:
+ Helpful in solving the problem of non-invertibility problem occuring when the number of data is insufficient as compared to that of the number of features.