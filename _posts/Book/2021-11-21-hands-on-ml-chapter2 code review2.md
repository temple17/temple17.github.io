---
title: Book Review - Hands on Machine Learning Chapter 2 Code review2
date: 2021-11-21 12:25:00
toc: true
toc_sticky: true
categories: Book
tags:
  - Book
  - ML
---
> `Code Review` handles concepts, unfamiliar codes for myself

> All of materials(quotes, images, definitions) are from this book.  
It's all just for self-study.

> Full codes are in my [github repository](https://github.com/temple17/hands-on-ml-practice) 

## 1. Select algorithm and train a model
1. Linear Regression Model

~~~python
from sklearn.linear_model import LinearRegression
lin_reg = LinearRegression()
# fit lin_reg to train and test set
lin_reg.fit(housing_prepared, housing_labels)
# prediction and measure RMSE
from sklearn.metrics import mean_squared_error
# predict with whole dataset
housing_predictions = lin_reg.predict(housing_prepared)
# mean_squared_error(correct target_values, estimated values)
lin_mse = mean_squared_error(housing_labels, housing_predictions)
lin_rmse = np.sqrt(lin_mse)
lin_rmse
~~~
> The result was not powerful enough, so try DecisionTreeRegressor instead

2. DecisionTreeRegressor Model

~~~python
from sklearn.tree import DecisionTreeRegressor
tree_reg = DecisionTreeRegressor()
# fit tree_reg to train and test set
tree_reg.fit(housing_prepared, housing_labels)
# prediction and measure RMSE
housing_predictions = tree_reg.predict(housing_prepared)
tree_mse = mean_squared_error(housing_labels, housing_predictions)
tree_rmse = np.sqrt(tree_mse)
tree_rmse
~~~
> The result was 0. So the model overfits the data.
> Need to use part of the training set for training and part for model validation.

### 2.1 Cross_val_score using `neg_mean_squared_error`
- The higher `tree_rmse_scores` becomes, the better model performs. 

## 3. RandomForestRegressor
~~~python
from sklearn.ensemble import RandomForestRegressor
forest_reg = RandomForestRegressor()
forest_reg.fit(housing_prepared, housing_labels)
housing_predictions = forest_reg.predict(housing_prepared)
forest_scores = cross_val_score(forest_reg, housing_prepared, housing_labels,
                                scoring = 'neg_mean_squared_error', cv = 10)
forest_rmse = np.sqrt(-forest_scores)
display_scores(forest_rmse)
~~~

> Continue on next page