---
title: Book Review - Hands on Machine Learning(C1-2)
date: 2021-09-04 12:25:00
toc: true
toc_sticky: true
categories: Book
tags:
  - Book
  - ML
---

> All of materials(quotes, images, definitions) are from this book.  
It's all just for self-study.

## Chapter 1
### Batch and Online learning

#### Batch learning(offline learning)
- incapable of learning incrementally
- take a lot of time and computing resources
- need to train a new version of the system from scratch on the full dataset(not just the new data, but also the old data)
  - then stop the old system and replace it with the new one

#### Online learning
- train the system incrementally
- each learning step is fast and cheap
- can learn about new data on the fly, as it arrives    
![](/assets/images/book/online learning.PNG)
- online learning is great for systems that receive data as a continous flow and need to adapt to change rapidly or autonomously    
![](/assets/images/book/online learning2.PNG)
- ***One important parameter of online learning systems is how fast they should adapt to changing data : learning rate***
  - set high learning rate : then system will rapidly adapt to new data, but it will also tend to quickly forget the old data
  - set low learning rate : then system will have more inertia, also be less sensitive to noise in the new data or to sequences of nonrepresentative data points(outliers)
- ***A big challenge with online learning is that if bad data is fed to the system, the system's performance will gradually decline***
- ***To reduce this risk, need to monitor your system closely and promptly switch learning off if you detect a drop in performance***

### Instance-Based vs Model-Based learning

#### Instance-Based learning
- The system learns the examples by heart, then generalizes to new cases by comparing them to the learned examples, using a similarity measure    
![](/assets/images/book/instance-based.PNG)

#### Model-based learning
- Build a model of these examples, then use that model to make predictions    
![](/assets/images/book/model-based.PNG)


- training the model : feed algorithm your training examples and it finds the parameters that make the model fit best to your data