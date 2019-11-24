---
layout: post
title: Recommendation Systems
tags: math cs
cover_url: https://532386f9a72d1dd857a8-41058da2837557ec5bfc3b00e1f6cf43.ssl.cf5.rackcdn.com/wp-content/uploads/2016/01/IMG_0082-1024x768.png
---

# What is a Recommendation System?

At its core, a recommendation system is a function that takes user data as input and outputs that user’s predicted rating for a set of products. The process of creating this system is complex and the subject of much research, but an overview will be provided here.

## Acquiring Training Data
Before a machine learning algorithm can be trained, the user data must be collected first. This often takes the form of prior user stated preferences, such as prior ratings or what they clicked on. We can represent these preferences in a utility matrix

Notably, the matrix is sparse, that is, many entries of the matrix will be empty since the majority of users have provided a preferences on a small fraction of potential product offerings. The goal of the recommendation system is to predict the missing values.

Separately, we acquire data on each products features $$X$$, for example the price, genre of movie, or color.

## Training the Classifier
A variety of classifier algorithms can be used, but for simplicity's sake, let us use a linear regression. For a given user $$u_i$$ we can fit a linear regression from product features $$X$$ to that user’s rating for that product. These linear regression coefficients, the parameters, give us information about that user’s preference for features. Now we have some information about each user’s preferences in terms of features rather than products.

## Collaborative Filtering
While the prior step gave us a very rudimentary look into user’s preferences, it does not exploit comparing one user to other users. If  two users preferences are similar to another, we can use that information to predict each other’s preferences. The process by which this is done is called collaborative filtering. First, we define a similarity metric, for example, the cosine distance between their preferences, to quantify the distance between two user’s preferences. We then predict a user’s preferences based on every other user’s preferences, weighted by similarity.

Again, this is a gross oversimplification with many details and steps, like data pre-processing, having been left out. There are also a litany of other, more involved, methods to perform the same tasks.

# Applications
Predicting customer preferences is practically the essence of marketing, and so there is a wealth of applications in marketing. These systems are ubiquitous and are one of the most successful examples of machine learning in marketing. The most familiar and canonical examples are Netflix’s recommendations that fill a user’s personalized “home page” and Amazon’s recommended products, but nearly every website you use has some form of a recommendation system running, from online dating sites, to research journals, to financial services, and insurance products. Just about everything you can imagine…

## The Long Tail
The recommendation system becomes more important the more products a company carries because of the “long tail” phenomenon. A company with only one product can only offer that single product, which while  it may popular, likely does not meet the complete demands of the market. As the number of differentiated products offered increases, the demands of the market are better met. Physical delivery systems are limited by physical limitations on how many SKUs they can offer, while online systems can offer a far greater number of SKUs. The long tail phenomenon describes the significance of the combined demand for all of the other non-popular SKUs which online systems can provide.

Given that online systems can have an immense number of product offerings, for example YouTube offers billions of videos, it is imperative that companies have a computational method of determining what a consumer’s preferences are.

## Segmentation
In some sense, the recommendation system is already a segmentation algorithm, but segmenting every single user into their own segment. Nonetheless, these recommendation systems can also be excellent as a method of clustering. By generating user’s preferences, it is easy to run segmentation algorithms to gain insights about the patterns of customers.