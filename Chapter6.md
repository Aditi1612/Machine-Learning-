# Chapter-6 : Logistic Regression
## Classification:
The classification problem is similar to that of the regression problem, except for the fact that the values we want to predict take on only a small number of discrete values. 
<br>
<br>
The values we want are in the range of 0 to 1 only, whereas in linear regression this is not possible, hence logistic regression is introduced as it uses the sigmoid function, so it values ranges from 0 to 1.

## Hypothesis representation:
The formula of the hypothesis representation : hθ(x) = 1 / (1 + e -θTx)
<br>
<br>
Interpreting hypothesis output: 
"When our hypothesis (hθ(x)) outputs a number, we treat that value as the estimated probability that y=1 on input x" 


## Decision boundary: 
A decision boundary is a line (in the case of two features), where all (or most) samples of one class are on one side of that line, and all samples of the other class are on the opposite side of the line. The line separates one class from the other.

## Non- linear decision boundaries:
More complex decision boundaries can be obtained by using the higher polynomial terms such as the circle shaped boundary.

## Cost function for logistic regression

The cost function for logistic regression uses the maximum likelihood estimation principle and is a convex function.

## How to minimize the logistic regression cost function
Since it is gradient descent, all θj must be updated at the same time.

Using a for loop is fine, but using a vector is more preferable and is much more faster.

## Advanced Optimisation:

Advantages:
+ We do not need to pick up the value of alpha manually.
+ Most of the time faster than the gradient descent.
+ Can be used without understanding the complexity.

Disadvantages:
+ Debugging is difficult
+ Different libraries may use different implementations.


## Multiclass classification problems:
When classifying multiple classes, one-to-many (One vs. All) classification is used.

When new data called x is added, predictive values ​​are obtained for all h functions of class i.

The class with the largest value becomes the class to which x belongs.