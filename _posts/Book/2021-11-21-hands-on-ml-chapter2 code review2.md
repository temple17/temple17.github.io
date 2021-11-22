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

## 1. Download the Data
1. `gzip`, `bz2`, `lzam` 압축과 `tar` 아카이브 파일을 읽고 쓰기
2. `urllib` 모듈을 활용하여 URL 작업 진행
~~~python
import tarfile
from six.moves import urllib
~~~
3. `HOUSING_PATH`는 파일이 저장될 경로를 지정하기 위해 사용
`HOUSING_ROOT`는 파일을 불러올 url을 지정
4. 디렉토리 생성 및 파일 불러오기
~~~python
def fetch_housing_data(housing_url = HOUSING_URL, housing_path = HOUSING_PATH):
    # directory가 없을 시 housing_paht 경로 생성
    if not os.path.isdir(housing_path):
        os.makedirs(housing_path)
    tgz_path = os.path.join(housing_path, "housing.tgz")
    # tgz_path라는 위치에 자료 저장
    urllib.request.urlretrieve(housing_url, tgz_path)
    # name에 대한 tarfile 객체를 반환함
    housing_tgz = tarfile.open(tgz_path)
    # extractall 함수로 여러 파일을 해제할 수 있음
    housing_tgz.extractall(path = housing_path)
    housing_tgz.close()
~~~
5. 저장된 파일 안에 있는 csv 파일 불러오기
~~~python
def load_housing_data(housing_path = HOUSING_PATH):
    csv_path = os.path.join(housing_path, "housing.csv")
    return pd.read_csv(csv_path)
~~~

## 2. Split train, test set
1. `StratifiedShuffleSplit` 층화추출
~~~python
from sklearn.model_selection import StratifiedShuffleSplit
# set test_size, random_state, split set n
# test/ train set -> n_splits = 1, test : 20% / train : 80%
split = StratifiedShuffleSplit(n_splits = 1, test_size = 0.2, random_state=42)
# return index of each datasets based on income_cat proportions
for train_index, test_index in split.split(housing, housing['income_cat']):
    strat_train_set = housing.loc[train_index]
    strat_test_set = housing.loc[test_index]
~~~

## 3. Handle categorical feature (ocean_proximity)
1. First way : `OrdinalEncoder`
~~~python
from sklearn.preprocessing import OrdinalEncoder
ordinal_encoder = OrdinalEncoder()
housing_cat_encoded = ordinal_encoder.fit_transform(housing_cat)
~~~
> `OrdinalEncoder`는 카테고리형 자료에 대해서 각각 0부터 길이만큼 번호를 부여함
> `fit_transform` 사용

2. Second way : `OneHotEncoder`
~~~python
from sklearn.preprocessing import OneHotEncoder
cat_encoder = OneHotEncoder()
housing_cat_1hot = cat_encoder.fit_transform(housing_cat)
~~~
> `OneHotEncoder`는 1과0의 성분만 가지는 행렬을 만든다.
> `fit_transform` 사용

## 4. Feature Scaling & Pipeline
1. First way : `StandardScaler`
~~~python
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import StandardScaler
num_pipeline = Pipeline([
                         ('imputer', SimpleImputer(strategy = 'median')),
                         ('attribs_adder', CombinedAttributesAdder()),
                         ('std_scaler', StandardScaler()),
])
housing_num_tr = num_pipeline.fit_transform(housing_num)
~~~

2. Second way : `ColumnTranformer` (Better)
~~~python
from sklearn.compose import ColumnTransformer
num_attribs = list(housing_num)
cat_attribs = ['ocean_proximity']
# num_pipeline : Scale number type columns
# OneHotEncoder : handle categorical data type
full_pipeline = ColumnTransformer([
                                   ('num', num_pipeline, num_attribs),
                                   ('cat', OneHotEncoder(), cat_attribs),
])
housing_prepared = full_pipeline.fit_transform(housing)
~~~
> How it works
  > 1. import the ColumnTransformer class
  > 2. get the list of numerical column names    
    and the list of categorical column names, and construct ColumnTransformer
  > 3. Finally apply this ColumnTrasformer to the housing data

> Continue on next page