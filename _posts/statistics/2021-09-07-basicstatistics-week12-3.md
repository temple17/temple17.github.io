---
title: KMOOC 통계학의 이해1 12주차-3
date: 2021-09-21 12:25:00
toc: true
toc_sticky: true
categories: statistics
tags:
  - KMOOC
---

# 이항분포의 정규근사

- X ~ B(n,p), n이 크고
  - p가 작은 경우 => 포아송 근사
  - p가 큰 경우 => 포아송 근사
  - p가 0.5에서 많이 벗어나지 않은 경우 => 정규근사
- X ~ B(n,p)   
![](/assets/images/statistics/poisson.PNG)  
![](/assets/images/statistics/poisson2.PNG)
- X ~ B(100,0.04)
  - E(X) = 4, Var(X) = 3.84   
  ![](/assets/images/statistics/poisson3.PNG) 
- X ~ B(100,0.4)
  - E(X) = 40, Var(X) = 24  
  ![](/assets/images/statistics/poisson4.PNG) 
- 이항분포는 이산형이고, 정규분포는 연속형
  - X가 연속확률변수이면
  - X가 이산확률변수이면   
![](/assets/images/statistics/poisson5.PNG)   
![](/assets/images/statistics/poisson6.PNG)    
=> ***연속성 수정(continuity correction)***




> 사진과 글은 KMOOC 사이트에서 숙명여대의 여인권 교수님의 [통계학의 이해1] 수업자료를 바탕으로 했습니다.  