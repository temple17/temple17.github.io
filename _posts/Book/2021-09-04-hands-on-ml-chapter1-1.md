---
title: Book Review - Hands on Machine Learning(C1-1)
date: 2021-09-04 12:25:00
toc: true
toc_sticky: true
categories: Book
tags:
  - Book
  - ML
---

> All of materials(quotes, images, definitions) are from this book.

## Chapter 1
### The Machine Learning Landscape

### Why use machine learning?

- training set : The examples that the system uses to learn
- training instance(or sample) : Each training example
- measure : The particular performance measure
> attribute : data type(ex: mileage) | feature : attribute + value(ex: mileage = 15,000)
- ![](/assets/images/book/ml approach.jpg)
- ***The best solution is to write an algorithm that learn by itself, given many example recordings for each word.***
- Data mining : Applying ML techniques to dig into large amounts of data can help discover patterns that were not immediately apparent

### Types of Machine Learning Systems

- Whether of not they are trained with human supervision
  - supervised
  - unsupervised
  - semisupervised
  - reinforcement
- Whether or not they can learn incrementally on the fly
  - online
  - batch
- Whether they work by simply comparing new data points to known data points,   
or instead detect patterns in the training data and build a predictive model,   
much like scientists do
  - instance-based
  - model-based

#### Supervised Learning
- The training data you feed to algorithm includes the desired solutions, called label
- Typical task
  - classification(spam vs ham)
  - regression : to predict target numeric value(price of a car)
    - predictors : given a set of features    
    - ![](/assets/images/book/regression.jpg)
- ***Some regression algorithms can be used for classification as well, and vice versa.***
- The most important supervised learning algorithms(covered in this book)    
![](/assets/images/book/impalgorithm.jpg)

#### Unsupervised Learning
- The training data is unlabeled
- The system tries to learn without a teacher
- The most important unsupervised learning algorithms(covered in chapter8 and 9)    
![](/assets/images/book/unsuperalgo.PNG)    
![](/assets/images/book/clustering.PNG)
- Typical task
  - dimensionality reduction
    - goal is to simplify the data without losing too much information   
    => feature extraction : merge several correlated features into one
  - anomaly detection(similar to novelty dection)
    - difference : anomaly detection is more tolerant
  -  association rule learning
    - goal is to dig into large amount of data and discover interesting relations between attributes

#### Semisupervised Learning
- some algorithms can deal with partially labeled training data,       
usually a lot of unlabeled data and a little bit of labeld data    
![](/assets/images/book/semisuper.PNG)
- most semisupervised learning algorithms are combinations of unsupervised and supervised algorithms


#### Reinforcement Learning
- The learning system(agent) in this context, can observe the environment, select and perform actions,    
and get rewards in turn(or penalties in the form of negative rewards)     
![](/assets/images/book/reinforcement.PNG)
