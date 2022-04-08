---
title: California housing price dataset EDA (1)
date: 2022-04-07 12:25:00
categories: EDA
toc: true
toc_sticky: true
tags:
  - EDA
---


> OREILLY 출판사의 Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow 2nd Edition
> Chapter 2의 End to end project에서 다루는 California 집값 데이터를 기반으로 하여 개인적으로 EDA를 재구성했습니다.    
> [A Comprehensive Guide to Data Exploration](https://www.analyticsvidhya.com/blog/2016/01/guide-data-exploration/)      
> [Simply statistics](https://simplystatistics.org/)   
> 위 사이트에서 좋은 자료들을 활용했고, 일부 코드는 교재에서 참고했습니다.

# EDA
**탐색적 자료 분석(Exploratory Data Analysis, EDA)**는 주어진 데이터를 면밀하게 탐색하는 과정을 통해 핵심 인사이트를    
추출하면서 이전보다 데이터를 더 잘 이해하기 위한 것입니다. 

구체적인 여러 방법론은 위의 링크를 참고하시면 도움이 많이 될 것입니다.

# EDA Framing
데이터가 주어지고, 곧바로 분석에 들어가는 것이 아니라, 데이터로부터 얻고자 하는 것이 무엇이고, 어떻게 접근할 것인지      
그림을 그리는 것이 중요한 단계입니다. 그리고 이 과정이 단순히 전형적인 EDA의 순서만 필요한 것이 아니라,    
**데이터를 바라보는 개인적인 역량과 시각**이 수반되어야 한다는 점에서 차별화를 둘 수 있습니다.   

## California housing price dataset

### 데이터 소개
해당 데이터는 캘리포니아 지역의 집값, 인구밀도, 침실의 개수, 경도와 위도 등 다양한 Feature를 지닌   
데이터 셋입니다. 이 데이터를 전처리하여 선형회귀모델을 만들어 집값을 예측하는 것이 교재에서 이루고자 하는   
목표입니다.

### 가설
1. 중위 소득이 높은 가구의 집값이 높을 것이다.
2. 바다와 인접한 집의 가격이 높을 것이다.
3. 침실과 화장실의 갯수가 많을수록 집값이 높을 것이다.

### 궁금증
1. 경도와 위도에 따른 집값의 분포는 어떨까?
2. 집값에 영향을 가장 많이 주는 feature는 무엇일까?
3. Null 값이 존재하는 feature는 무엇이고, 있다면 어떻게 처리할 것인가?
4. Null 값이 없지만, 모든 데이터가 정상적으로 채워져 있는가?
5. 집값이 높은 집과 낮은 집의 특징을 결과적으로 찾아낼 수 있는가?
6. 어떤 시각화를 적용할 수 있는가? 그리고 어떤 라이브러리를 활용할 것인가?

#### 단계
[A Comprehensive Guide to Data Exploration](https://www.analyticsvidhya.com/blog/2016/01/guide-data-exploration/) 에서   
참고한 EDA의 단계는 총 7단계입니다.   

1. Variable Identification
2. Univariate Analysis
3. Bi-variate Analysis
4. Missing values Tretatment
5. Outlier treatement
6. Variable transformation
7. Variable creation

단계마다 포함된 세부 방법론을 활용해서 다양한 시각화와 데이터 탐색을 할 예정입니다.

코랩 노트북은 [제 깃헙](https://github.com/temple17/self-review/blob/58f253eae2ca37555a6b52025b94eaa69e2f2268/California_housing_price.ipynb)에 업로드 되어 있습니다.        

*Just do it & Keep steady*
