---
title: KMOOC 통계학의 이해1 8주차-3
date: 2021-08-24 12:25:00
toc: true
toc_sticky: true
categories: statistics
tags:
  - KMOOC
---

# 공분산과 상관계수

## 기댓값

![](/assets/images/statistics/expectation6.PNG)  
- 확률변수 X와 Y에 대해, X+Y의 기댓값? XY의 기댓값?  
두 변수를 고려한다는 것은 일단 두 변수에 대한 결합분포가 있다는 것을 전제  
=> 결합확률질량함수나 결합확률밀도함수를 이용
- 이산확률변수  
![](/assets/images/statistics/expectation7.PNG)  

### 기댓값 정리
1. E(X+Y) = E(X) + E(Y)
2. X와 Y가 독립이면 E(XY) = E(X)E(Y)

## 공분산(covariance)
![](/assets/images/statistics/covariance5.PNG)  
- 두 확률변수 X와 Y의 공분산  
![](/assets/images/statistics/covariance6.PNG)  
  - 역은 일반적으로 성립하지 않음

### 기댓값 정리
![](/assets/images/statistics/expectation8.PNG)

## 상관계수(coefficient of correlation)
- 표준화 변수들의 공분산  
![](/assets/images/statistics/coefficientcorr3.PNG)
- 두 확률변수 X와 Y의 상관계수  
![](/assets/images/statistics/coefficientcorr4.PNG)

- 상관계수의 성질  
![](/assets/images/statistics/coefficientcorr5.PNG)




> 사진과 글은 KMOOC 사이트에서 숙명여대의 여인권 교수님의 [통계학의 이해1] 수업자료를 바탕으로 했습니다.  
