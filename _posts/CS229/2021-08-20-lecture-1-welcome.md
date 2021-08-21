---
title: CS229 Lecture 1 - Welcome
date: 2021-08-20 12:25:00
toc: true
toc_sticky: true
categories: CS229
tags:
  - CS229
  - ML
---


# "ML & AI will change the world."

## Goal of this lecture
Be the expert in machine learning.  
But machine learning is so pervasive.  

## Prerequisite
- Big O notation
- Queue, stacks, and binary trees
- Basic with probability
- Basic linear algebra & eigenvector  

## Best part of CS229
- class project
  - complete meaningful ML project as a team
> Using convex optimization algorithm is the main key

## CSxxx class difference
- CS229 : most mathmethical
- CS229a : less math than CS229
- CS231n : mostly about deep learning

## Quick overview
"Machine learning is everywhere.   
Do meaningful work and take the opportunity of superpower."

### Supervised learning
- used in solving a regression problem & classification problem
- X -> Y
- In actual study, there are multiple features which consist high-dimension
- SVM(support vecotr machine) allows infinite dimesion vector(learn in next lectures)

#### Regression problem
- Y is continous value
- Example : predicting housing price
  - X : size(squared feet) / Y : price

#### Classification problem
- Y is discrete value
- Example : classifying breast tumor
  - X : tumor size / Y : malignancy(0 : non-malignant, 1: malignant)

> Input X, label Y -> find mapping(+ X is given) -> Return new Y

### Unsupervised learning
- Input X, and no label Y
- Find interesting pattern of characteristic by its own
- Example : Cocktail party problem(using ica algorithm)
  - How to seperate voices? (Clustering)

### Reinforcement learning
- Don't know optimal ways
- Keep training

## Conclusion
The model looks like this
![](/assets/images/cs229/CS229.jpg){: .align-center}
