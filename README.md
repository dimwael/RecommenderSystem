# RecommenderSystem

A recommender system refers to a system that is capable of predicting the future preference of a set of items for a user, and recommend the top items. One key reason why we need a recommender system in modern society is that people have too much options to use from due to the prevalence of Internet. In the past, people used to shop in a physical store, in which the items available are limited. For instance, the number of movies that can be placed in a Blockbuster store depends on the size of that store. By contrast, nowadays, the Internet allows people to access abundant resources online. Netflix, for example, has an enormous collection of movies. Although the amount of available information increased, a new problem arose as people had a hard time selecting the items they actually want to see. This is where the recommender system comes in. This article will give you a brief introduction to two typical ways for building a recommender system, Collaborative Filtering and Singular Value Decomposition.

![Recommender System](https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2018/05/0o0zVW2O6Rv-LI5Mu.png)

# Traditional Approach

Traditionally, there are two methods to construct a recommender system :

    * Content-based recommendation
    * Collaborative Filtering

The first one analyzes the nature of each item. For instance, recommending poets to a user by performing Natural Language Processing on the content of each poet. Collaborative Filtering, on the other hand, does not require any information about the items or the users themselves. It recommends items based on users’ past behavior. I will elaborate more on Collaborative Filtering in the following paragraphs.

# Collaborative Filtering

As mentioned above, Collaborative Filtering (CF) is a mean of recommendation based on users’ past behavior. There are two categories of CF:

    User-based: measure the similarity between target users and other users
    Item-based: measure the similarity between the items that target users rates/ interacts with and other items

The key idea behind CF is that similar users share the same interest and that similar items are liked by a user.

Assume there are m users and n items, we use a matrix with size m*n to denote the past behavior of users. Each cell in the matrix represents the associated opinion that a user holds. For instance, M_{i, j} denotes how user i likes item j. Such matrix is called utility matrix. CF is like filling the blank (cell) in the utility matrix that a user has not seen/rated before based on the similarity between users or items. There are two types of opinions, explicit opinion and implicit opinion. The former one directly shows how a user rates that item (think of it as rating an app or a movie), while the latter one only serves as a proxy which provides us heuristics about how an user likes an item (e.g. number of likes, clicks, visits). Explicit opinion is more straight-forward than the implicit one as we do not need to guess what does that number implies. For instance, there can be a song that user likes very much, but he listens to it only once because he was busy while he was listening to it. Without explicit opinion, we cannot be sure whether the user dislikes that item or not. However, most of the feedback that we collect from users are implicit. Thus, handling implicit feedback properly is very important, but that is out of the scope of this blog post. I’ll move on and discuss how CF works.
User-based Collaborative Filtering

We know that we need to compute the similarity between users in user-based CF. But how do we measure the similarity? There are two options, Pearson Correlation or cosine similarity.
