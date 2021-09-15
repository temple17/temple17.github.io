---
title: KMOOC 통계학의 이해1 11주차-1
date: 2021-09-14 12:25:00
toc: true
toc_sticky: true
categories: statistics
tags:
  - KMOOC
---

# 정규분포와 확률계산

## 정규분포(Noraml Distribution)

### Gaussian distribution
- 평균(뮤)와 분산(시그마 제곱)에 따른 정규분포의 확률밀도 함수 => ![](/assets/images/statistics/normal.PNG)    
![](/assets/images/statistics/normal2.PNG)
- 확률계산: P(a < X < b) =?   
![](/assets/images/statistics/normal3.PNG)

## 표준정규분포(standard normal distribution)

![](/assets/images/statistics/snormal.PNG)
  - 일반적으로 Z로 표시: Z ~ N(0,1)
- 확률계산:   
![](/assets/images/statistics/snormal2.PNG)
  - 수치해석학적으로 계산
  - 표준정규분포표 사용
- 표준정규분포의 확률계산 문제
  - 0을 중심으로 대칭이라는 사실을 이용
    - P(Z<=a), P(Z>a), P(a< Z <= b)
- a가 주어지고 P(Z > z) = a를 만족하는 z(분위수) 계산   
![](/assets/images/statistics/snormal3.PNG)

> 사진과 글은 KMOOC 사이트에서 숙명여대의 여인권 교수님의 [통계학의 이해1] 수업자료를 바탕으로 했습니다.  