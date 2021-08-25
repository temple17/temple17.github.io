---
title: KMOOC 기초통계 8주차-1
date: 2021-08-24 12:25:00
toc: true
toc_sticky: true
categories: statistics
tags:
  - KMOOC
---

# 분산과 표준편차

## 모분산(population variance)

### 표본분산
- 표본크기 : n
- 표본이 가질 수 있는 값 {x1,x2,..,xk}
- ni : 표본 중 xi 값을 가지는 표본의 수   
![](/assets/images/statistics/population variance.png)  
  - pi = ni/n
- n을 계속 크게 하면
  ![](/assets/images/statistics/population variance1.png)  
- 모분산을 시그마제곱으로 표시  
  ![](/assets/images/statistics/population variance2.png)  
- 확률변수 X의 분산을 Var(X)로 표시  
  ![](/assets/images/statistics/population variance3.png)  

### 연속확률변수 X의 분산  
![](/assets/images/statistics/population variance4.png)  
- Var(aX+b) = a^2Var(X)  
![](/assets/images/statistics/population variance5.png)  
  - 위치의 변화를 주는 상수 b는 분산에 영향을 주지 않ㅎ음
  - 분산은 측정단위의 제곱이기 때문에 a의 제곱을 곱합
  - ![](/assets/images/statistics/population variance6.png)  

### X~U(0,1) : Uniform distribution
- 구간(0,1)에서 균등하게 분포 => 균일(균등)분포
- E(X) = 1/2
- E(X^2) = 1/3 => Var(X) = 1/12

> 사진과 글은 KMOOC 사이트에서 숙명여대의 여인권 교수님의 [통계학의 이해1] 수업자료를 바탕으로 했습니다.  
