---
title: Book Review - Hands on Machine Learning Chapter 2 Code review3
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

## 1. Fine Tune Model
>In this step, all I need to do is tell in which hyperparameters 
I want it to experiment with, and what values to try out, and it will evaluate
all the possible combinations of hyperparameter values using cross_validation

### 1. GridSerachCV
~~~python
from sklearn.model_selection import GridSearchCV
param_grid = [
              {'n_estimators': [3,10,30], 'max_features':[2,4,6,8]},
              {'bootstrap': [False], 'n_estimators': [3,10], 'max_features': [2,3,4]},
]
forest_reg = RandomForestRegressor()
grid_search = GridSearchCV(forest_reg, param_grid, cv = 5,
                           scoring = 'neg_mean_squared_error',
                           return_train_score = True)
grid_search.fit(housing_prepared, housing_labels)
~~~
> Need more study about GridSearchCV

## 2. Evaluate the test set
~~~python
final_model = grid_search.best_estimator_
X_test = strat_test_set.drop('median_house_value', axis = 1)
y_test = strat_test_set['median_house_value'].copy()
# transform using full_pipeline
X_test_prepared = full_pipeline.transform(X_test)
final_predictions = final_model.predict(X_test_prepared)
final_mse = mean_squared_error(y_test, final_predictions)
final_rmse = np.sqrt(final_mse)
~~~

## 3. Hard parts for me
- custom transformation : `class CombinedAttributesAdder`
- Pipeline
- GridSearchCV

> Continue on next page