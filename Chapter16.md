# Chapter-16: Recommender Systems
## Recommender system s- introduction

One of the most used algorithm today. Used on shopping sites such as Amazon, Ebay etc.

Recommender systems try and identify the crucial and relevant features.

### Example- predict movie ratings:
Have 4 users rate 5 movies.

? means that you have not evaluated the film.

Here,
nu - Number of users (called ?nu occasionally as we can't subscript in superscript)
nm - Number of movies
r(i, j) - 1 if user j has rated movie i (i.e. bitmap)
y(i,j) - rating given by user j to move i (defined only if r(i,j) = 1

Summary of scoring
+ Alice and Bob gave good ratings to rom coms, but low scores to action films
+ Carol and Dave game good ratings for action films but low ratings for romance films.

The problem is as follows:
+ Given r(i,j) and y(i,j) - go through and try and predict missing values (?s)
+ Come up with a learning algorithm that can fill in these missing values

## Content based recommendation:
+ For each movie we have a feature which measure degree to which each film is a 
>>> + Romance (x1)
>>> + Action (x2)

If you look at the feature vector from the first movie, Love at last, x0 has a value of 1 in bias.

x(1) = [1, 0.9, 0]
This creates a data set from x1 to x5.

In addition, if the parameter for each user is set to θ, this θ becomes a vector indicating the user's inclination.

θ(1) = [0, 5, 0]
Therefore, if we multiply the feature vector of the movie by the θ vector of the user, we get the star information.

(θj) T * xi = stars
Now let's predict the star rating of Cute puppies of love, which Alice didn't rate.

(θ(1)) T * x3 = (0 * 1) + (5 * 0.99) + (0 * 0) = 4.95


### How do we learn (θj):
+ Sum over all values of i (all movies the user has used) when r(i,j) = 1 (i.e. all the films that the user has rated)
+ This is just like linear regression with least-squared error.
+ In order to do the minimization, we have slightly different gradient descent where we have k =0 and k!=0 versions. 


Difference from linear regression:
+ No 1/m terms 


This appproach is called the content based approach because we assume we have features regarding the content which will help us identify things that make them appealing to a user.


## Collaborative filtering- overview:
The collaborative filtering does the feature learning i.e it can learn for itself what the features needs to learn

These parameters can fill in the features associated with the movie.

If you watch the movie Love at Last, Alice and Bob, who love romance, gave it a high score.

Carol and Dave, who dislike romance, also gave it a low score.

Therefore, we can conclude that Love at Last is a romance movie.


### Formalizing the collaborative filtering problem:
+ Given (θ1, ..., θnu) (i.e. given the parameter vectors for each users' preferences)
+ We must minimize an optimization function which tries to identify the best parameter vector associated with a film
+ So we're summing over all the indices j for where we have data for movie i
+ We're minimizing this squared error 



### How does this work with the previous recommendation system:

1. Randomly guess values for θ
2. Then use collaborative filtering to generate x
3. Then use content based recommendation to improve θ
4. Use that to improve x
5. And so on

This is called the collabarative filtering because here we are collaborating together in order to learn better features of the algorithm.


## Collaborative filtering Algorithm:
1) Initialize θ1, ..., θnu and x1, ..., xnm to small random values
A bit like neural networks - initialize all parameters to small random numbers
2) Minimize cost function (J(x1, ..., xnm, θ1, ...,θnu) using gradient descent
We find that the update rules look like this
3)  Having minimized the values, given a user (user j) with parameters θ and movie (movie i) with learned features x, we predict a start rating of (θj)T xi 

## Vectorization: Lowrankl matrix factorization: 
In order to improve the collaborative filtering algorithm, we can determine other relevant products.


Since there are 5 movies and there are 4 users, they are represented by a matrix of [5 X 4].

You can define another matrix x.

It's about taking all the features of each movie and stacking them.

There is also another matrix θ.

All the parameters of each user are taken and stacked.

We can predict the rating information by calculating x * θT given the new matrices x and θ.

This x matrix and the θ matrix are called low rank matrix, and the algorithm for this method is called low rank matrix factorization.


## Implementation detail: Mean nor,malization:

Considering an example where there is a user(Eve) who has not rated any movies.


Since Eve has no film left a rating, r(i, j) will all be 0.

Therefore, only the normalization part of the formula remains. And if you minimize this, of course θ becomes 0.

In the end, θT * x will also be 0, so the expected rating of all films will be zero.

This creates a problem where new users who don't have rating information can't recommend other movies.

Mean normalization is needed to solve problems like this.