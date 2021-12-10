# Book-Recommendation-System

![image](https://user-images.githubusercontent.com/60726057/127698429-1b47dc19-2931-428b-95ca-2ef2f6a4c5b2.png)

## Problem Statement:

During the last few decades, with the rise of Youtube, Amazon, Netflix, and many other such web services, recommender systems have taken more and more place in our lives. From e-commerce (suggest to buyers articles that could interest them) to online advertisement (suggest to users the right contents, matching their preferences), recommender systems are today unavoidable in our daily online journeys.
In a very general way, recommender systems are algorithms aimed at suggesting relevant items to users (items being movies to watch, text to read, products to buy, or anything else depending on industries).
Recommender systems are really critical in some industries as they can generate a huge amount of income when they are efficient or also be a way to stand out significantly from competitors. The main objective is to create a book recommendation system for users.

Here I've built book recommendation system for users based on popularity and user interests.

# Dataset Information:
● Users
This .csv file contains the users. Note that user IDs (User-ID) have been anonymized and map to integers. Demographic data is provided (Location, Age) if available. Otherwise, these fields contain NULL values.
● Books
Books are identified by their respective ISBN. Invalid ISBNs have already been removed from the dataset. Moreover, some content-based information is given (Book-Title, Book-Author, Year-Of-Publication, Publisher), obtained from Amazon Web Services. Note that in the case of several authors, only the first is provided. URLs linking to cover images are also given, appearing in three different flavors (Image-URL-S, Image-URL-M, Image-URL-L), i.e., small, medium, large. These URLs point to the Amazon website.
● Ratings
Contains the book rating information. Ratings (Book-Rating) are either explicit, expressed on a scale from 1-10 (higher values denoting higher appreciation), or implicit, expressed by 0.

# Model Creation

## 1)Popularity Based Approach:
It is a type of recommendation system which works on the principle of popularity and or anything which is in trend. These systems check about the books which are in trend or are most popular among the users and directly recommend them.
For example, if a product is often purchased by most people then the system will get to know that that product is most popular so for every new user who just signed it, the system will recommend that product to that user also and chances become high that the new user will also purchase that.

A popularity based model does not suffer from cold start problems which means on day 1 of the business also it can recommend products on various different filters. There is no need for the user’s historical data.
Now let's try to build our first recommendation system based on popularity. These
systems check about the product which are in trend or are most popular among the
users and directly recommend those.

We can see the top 10 books recommendation on basis of popularity.

![image](https://user-images.githubusercontent.com/60726057/145525852-d99df7ea-f1a1-4fea-a2e5-9c8422d0e146.png)

## 2)Collaborative Filtering Using KNN (k-Nearest Neighbors)
kNN (k-Nearest Neighbors) as an algorithm seems to be inspired from real life. The full k-Nearest Neighbors algorithm works much in the way some of us ask for recommendations from our friends. First, we start with people whose taste we feel we share, and then we ask a bunch of them to recommend something to us. If many of them recommend the same thing, we deduce that we’ll like it as well. Our behavior is guided by the friends we grew up with kNN is a machine learning algorithm to find clusters of similar users based on common book ratings, and make predictions using the average rating of top-k nearest neighbors.
KNN does not make any assumptions on the underlying data distribution but it relies on item feature similarity. When KNN makes inference about a movie, KNN will calculate the “distance” between the target book and every other book in its database, then it ranks its distances and returns the top K nearest neighbor movies as the most similar book recommendations.

![image](https://user-images.githubusercontent.com/60726057/145527928-425266df-b3aa-44ae-b757-a0fcf3d55699.png)

Here we assume that users who given ratings more than 200 are users who read at least 20 books (suppose on user given rating 10/10 so minimum he read books (200 ratings/10 ratings per book=20).Hence for statistical significance we should consider only the data of user who given more than 200 ratings.

## After that we test the model and make recommendations:
### Recommendation for random book:
![image](https://user-images.githubusercontent.com/60726057/145528196-93fd5848-a8b5-43d4-9a34-14c1b84d91f5.png)

### Recommendation for known book from dataset:
![image](https://user-images.githubusercontent.com/60726057/145528251-fdcd2684-41ce-4dfd-9858-5b4fad277bb9.png)

Here we can see that we have good recommendation the distance describes the closeness of the book with the recommended books.

## 3)Singular Value Decomposition (SVD):

Singular value decomposition also known as the SVD algorithm is used as a collaborative filtering method in recommendation systems. SVD is a matrix factorization method that is used to reduce the features in the data by reducing the dimensions from N to K where (K<N).
For the part of the recommendation, the only part which is taken care of is matrix factorization that is done with the user-item rating matrix. Matrix-factorization is all about taking 2 matrices whose product is the original matrix. Vectors are used to represent item ‘qi’ and user ‘pu’ such that their dot product is the expected rating as given below,

![image](https://user-images.githubusercontent.com/60726057/145528437-d67ac722-50c5-4eae-a2f0-2e6b6b737e2d.png)

qi’ and ‘pu’ can be calculated in such a way that the square error difference between the dot product of user and item and the original ratings in the user-item matrix is least.

### Benefits of using SVD?
There are 3 primary benefits :
● It’s very efficient
● The basis is hierarchical, ordered by relevance
● It tends to perform quite well for most data sets
Surprise is a Python scikit for building and analysing recommender systems that deal with explicit
Rating data. The name SurPRISE (roughly) stands for Simple Python Recommendation System
Engine.

Recommendation by giving user-id as input:
On picking a random user_id = 116866 our model recommend this books 
![image](https://user-images.githubusercontent.com/60726057/145528592-85399662-6cce-467e-966a-03b672790583.png)

Above recommended books seems pretty much related.

# CHALLENGES
• Understanding the metric for evaluation was a challenge as well.
• Decision making on missing value imputations quite challenging.
• Handling of sparsity was a major challenge.

# CONCLUSION
● Recommendation system is unturned to exist in the e-commerce businesses with the help of collaborative or content-based filtering to predict different items and yes, users     are most satisfied with the products recommended to them.
● Books with publication years are somewhat between 1950 - 2005.
● Also the readers mostly give 8 ratings (on scale 1-10) to books followed by 10 and 7.
● There are more readers from locations London, England, United Kingdom, Toronto, ontar io, Canada compare to other locations.
● KNN model gives good recommendation for books.
● The best collaborative book recommender model is SVD(Singular value decomposition) with best accuracy on test data which give stronger recommendations. These results show that our proposed system can remove boring books from the recommendation list more efficiently.
