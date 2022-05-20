# Chapter - 4: Linear Regression with Multiple Variables

## Linear Regression with multiple features:
Until now, results were predicted using two parameters and one variable x. But we can have multiple features in order to predict the results.
<br>
If there are multiple variables, theta and x are expressed as vectors. Hence, the function h can also be expressed as a product of theta vector and x vector.
<br>
Transpose of theta vector is a column vector with size [1 X n+1], and vector x is a row vector with size [n+1 X 1].
<br>
Since the multiplication operation cannot be performed between vectors having the same direction, the theta vector is transposed.

## Gradient Descent : Feature Scaling
Gradient Descent performs better in convergence if all the variables are in a similar range, not necessarily the same range.
<br>
The values can be adjusted in order to obtain a similar range. 
<br>
Methods of adjusting in order to obtain a similar range:
1) Feature Scalling : defining each value from x1 and x2 by dividing by the max for each feature.
+ Countours will become more like circles.+ May want to get everything in the range -1 to +1.
2) Mean normalisation : Taking  a feature xi
+ Replace it by (xi - mean)/max.
+ So that your values all have an average of about 0.

## Feature and polynomial regression:
It is not necessary to use only the given variables. You can create a new variable using the given variables and use it. A newly created variable may be a better indicator.

## Normal equation:
J(theta) = a(theta)2 + b(theta) + c

Differentiate by theta to find the minimum of the above expression.

Find the theta value for which the derivative is zero.

The theta value is the minimum value of J (theta).

## When should you use gradient descent and when should you use feature scaling?
Gradient descent:
+ Need to chose learning rate
+ Needs many iterations - could make it slower

Normal equation
+ No need to chose a learning rate
+ No need to iterate, check for convergence etc.
+ Normal equation needs to compute (XT X)-1
+ Slow of n is large
