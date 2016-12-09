# Wine Recommendation System  
There is an extensive class of Web applications that involve predicting user
responses to options. Such a facility is called a recommendation system.Two good
examples of recommendation systems are:
1. Offering news articles to on-line newspaper readers, based on a prediction
of reader interests.
2. Offering customers of an on-line retailer suggestions about what they
might like to buy, based on their past history of purchases and/or product
searches.

Recommendation systems use a number of different technologies. We can
classify these systems into two broad groups.
- Content-based systems examine properties of the items recommended. For
instance, if a Netflix user has watched many cowboy movies, then recommend
a movie classified in the database as having the “cowboy” genre.
- Collaborative filtering systems recommend items based on similarity measures
between users and/or items. The items recommended to a user are
those preferred by similar users. However, these technologies by themselves are not suffi-
cient, and there are some new algorithms that have proven effective for
recommendation systems.

We have used K-means clustering to give recommendation to users

## Requirements

* [Python 3.5](https://docs.python.org/3/)
* [django](https://www.djangoproject.com/)
* [SciPy](https://api.mongodb.com/python/current/)
* [Bootstrap3](http://django-bootstrap3.readthedocs.io/en/latest/)
* [sklearn](http://scikit-learn.org/)
* [numpy](http://www.numpy.org/)
* [panadas](http://pandas.pydata.org/)

## Stages

- [**stage-0**](#!): Created an empty project.  
- [`stage-0.1`](#!): A Django project with one app called `reviews`. The app defines model entities.  
- [`stage-0.2`](#!): Added Admin site up and running for our model entitities `Wine` and `Review`.  
- [`stage-0.3`](#!): Added views and templates.  
- [`stage-0.4`](#!): Added review form.
- [`stage-0.5`](#!): Reusing template.  
- [**stage-1**](#!): Added Bootstrap 3 for Django.  
- [`stage-1.1`](#!): `add_review` now requires login. Added login templates and menu sesion links.   
- [`stage-1.2`](#!): Added a user reviews page created.  
- [**stage-2**](#!): user management done.  
- [`stage-2.1`](#!): Added Scripts to load CSV available + data loaded.  
- [`stage-2.2`](#!): An empty wine suggestions view has been added.  
- [`stage-2.3`](#!): Suggestions view now shows wines not reviewed by the user.  
- [`stage-2.4`](#!): Added cluster model object and manually created three clusters.  
- [`stage-2.5`](#!): Suggestions view now makes use of cluster information.  
- [**stage-3**](#!): K-means clustering based recommendations provided.    

## Datasets

The dataset we to used is provided by [CellarTracker](http://www.cellartracker.com/). It consists of 2,025,995
wine reviews from CellarTracker, involving 44,268 users and 485,179 kinds of wines. Every piece of review data includes 9 cells of information:
1. name of the wine
2. wine unique id
3. reviewers name
4. reviewers id
5. rating
6. the review text

## Steps in brief
1. **User Authenticatio**  
User have to register in our webapp
2. **Reviews**  
User have to give reviews of the products listed in our webapp
3. **Clustering Users**  
Clustering users on the basis of same user preferences/reviews
4. **Recomendation**  
User can check recommendations on the basis of reviews he/she had given

## Using k-means clustering to provide better recommendations
There are at least two other ways we can make recommendations that improve the previous naive approach. Both of them require us to know our friend's preferences. In the first approach, we ask user to tell us a few wines he/she liked and, based on our knowledge about these wines, we recommend user wines that are similar. This requires a good amount of knowledge about wine. It is what a good and experienced wine store owner would do, and suggestions are hard to improve by a computer that follows the same approach due to many unknown factors that are involved in this kind of customer relationship.

There is a second approach that doesn't require any knowledge about wine, but one only needs to know what other people like and dislike (and not just that of our friend/customer). With that knowledge, we just try to find a person with similar preferences to our friend. Then we ask that second person for user's favourite wines and suggest them to our first friend, not including those that our first friend have already tried. We just act as an intermediary, and a computer system here can do the job better than any human being since it can "ask" millions of people in short time.

This is what our system will do, and we will use clustering for that. Why? Simple. Instead of trying to compare our user to every other user in the system every time recommendations are needed, we will pre-cluster all the users in the system by its wine reviews scores. By doing so we will have groups of similar users. Then, when a user asks for recommendations, we will look for them just in the cluster this user is clustered in. Since we know all the users in that cluster have a similar taste (they scored similarly the same wines, for good or bad), this greatly reduces the search space.

Of course there are more sophisticated recommender systems (e.g. collaborative filtering using ALS), but this one is easy to understand in terms of its meaning and makes use of some machine learning techniques we already know about.  

### Setting up project
```
$ git pull https://github.com/vaibhavsingh97/Winerma.git
```
## Running the server with runserver

```
$ python manage.py runserver 0.0.0.0:8000
```
Then we can go to our localhost server public URL http://localhost:8000
## Supporting Research paper
* [Movie Recommendations from User Ratings](http://cs229.stanford.edu/proj2013/Bystrom-MovieRecommendationsFromUserRatings.pdf) - Hans Byström
* [An Improved Recommendation Algorithm in Collaborative Filtering](http://link.springer.com/chapter/10.1007/3-540-45705-4_27)- Taek-Hun Kim, Young-Suk Ryu, Seok-In Park, Sung-Bong Yang

## Contributiors
* [Shreya Garg](#!)
* [Vaibhav Singh](github.com/vaibhavsingh97/)
