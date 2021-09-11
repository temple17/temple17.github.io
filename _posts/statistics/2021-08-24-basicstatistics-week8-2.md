---
title: KMOOC 기초통계 8주차-2
date: 2021-08-24 12:25:00
toc: true
toc_sticky: true
categories: statistics
tags:
  - KMOOC
---

# 결합분포와 주변분포

## 결합분포(joint distribution)
- 두 개 이상의 확률변수들을 동시에 고려한 확률분포
- 두 이산확률변수 X와 Y에 대해  
f(x,y) = P(X=x, Y=y)
  - f(x,y) : 결합확률질량함수
- n개의 이산확률변수 X1,...,Xn에 대해  
f(x1,...,xn) = P(X1 = x1,...,Xn = xn) 
- 두 연속확률변수 X와 Y에 대해, 결합확률밀도함수 f(x,y)는 x,y에서의 밀도를 나타내며 아래의 성질을 만족  
![](/assets/images/statistics/joint distribution2.PNG)    
![](/assets/images/statistics/joint distribution3.PNG)  

### 동전 세 번 던지기
- X : 앞면의 수, Y : 앞면과 뒷면의 수의 차이  
![](/assets/images/statistics/joint distribution.PNG)  

## 주변분포(marginal distribution)
- 표본공간이 사건 B1,..., Bn로 분할될 때 사건 A의 확률은  
![](/assets/images/statistics/marginal distribution.PNG)    
![](/assets/images/statistics/marginal distribution1.PNG)    
- 연속확률변수 : 주변확률밀도함수  
![](/assets/images/statistics/marginal distribution2.PNG)    
- (X,Y) ~ U((0,u),(0,v))  
![](/assets/images/statistics/marginal distribution3.PNG)    

# 독립 확률변수
- 사건 A와 B는 독립 
- 두 확률 변수 X와 Y는 독립 => 모든 x,y에 대해  
![](/assets/images/statistics/independent variable.PNG)    

> 사진과 글은 KMOOC 사이트에서 숙명여대의 여인권 교수님의 [통계학의 이해1] 수업자료를 바탕으로 했습니다.  
