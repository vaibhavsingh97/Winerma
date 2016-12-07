# Wine Recommendation System  
There is an extensive class of Web applications that involve predicting user
responses to options. Such a facility is called a recommendation system. We
shall begin this chapter with a survey of the most important examples of these
systems. However, to bring the problem into focus, two good examples of
recommendation systems are:
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
those preferred by similar users. This sort of recommendation system can
use the groundwork laid in Chapter 3 on similarity search and Chapter 7
on clustering. However, these technologies by themselves are not suffi-
cient, and there are some new algorithms that have proven effective for
recommendation systems.


## Requirements

* [Python 3.5](https://docs.python.org/3/)
* [SciPy](https://api.mongodb.com/python/current/)
* [Bootstrap3](http://django-bootstrap3.readthedocs.io/en/latest/)
* [sklearn]()
* [numpy]()
* [panadas]()

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



1. First creting project using django  
```
$ django-admin.py createproject ProjectName
```

2. d

## Run

```
$ python manage.py runserver 0.0.0.0:8000
```
## Contributiors
* [Shreya Garg](#!)
* [Vaibhav Singh](github.com/vaibhavsingh97/)
