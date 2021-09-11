---
title: Book Review - Hands on Machine Learning(C2-2)
date: 2021-09-10 12:25:00
toc: true
toc_sticky: true
categories: Book
tags:
  - Book
  - ML
---

> All of materials(quotes, images, definitions) are from this book.  
It's all just for self-study.

# Look at the big picture

## Frame the Problem
- First question to ask : ***what exactly is the business objective***
- How does the company expect to use and benfit from this model?

> pipeline : a sequence of data processing components

- Second question to ask : ***what the current solution looks like (if any)***
- will often give a reference performance, as well as insights on how to solve the problem
> - typical supervised learning task(with labeld data)  
> - typical regression task(predict a value)  
> - multiple regression problem : use multiple features to make a prediction   
> - also a univariate regression problem : predict a single value for each district       
> - plain batch learning   

### Select a Performance Measure
1. RMSE(Root Mean Square Error) : corresponds to the Euclidean norm
2. MAE(Mean Absolute Error) : corresponds to the Manhattan norm
- The higher the norm index, the more it focuses on large values and neglects samll ones
  - This is why RMSE is more sensitive to outliers than the MAE
  - But when outliers are exponentially rare(like in a bell-shaped curve), the RMSE performs very well and is generally preferred

### Check the Assumptions
- We need actual values of each district for our prediction(not category e.g., "cheap","medium","expensive)

### Get the Data & Create the Workspace
- I'm gonna use google colab instead using jupyter notebook

### Download the Data 
- From this part, I'll upload this notebook on my github

# This is my [github repository](https://github.com/temple17/hands-on-ml-practice)