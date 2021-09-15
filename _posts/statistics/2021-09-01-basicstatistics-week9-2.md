---
title: KMOOC 통계학의 이해1 9주차-2
date: 2021-09-01 12:25:00
toc: true
toc_sticky: true
categories: statistics
tags:
  - KMOOC
---

# 이항분포(Binomial distribution)


- 성공할 확률이 p인 베르누이 실험을 n번 반복했을 때 성공 횟수(X)의 분포
- Xi ~ B(p)라고 할 때, 성공 횟수 X는 n개의 베르누이 확률변수를 합으로 표시  
![](/assets/images/statistics/binomial.PNG)
- 기댓값
![](/assets/images/statistics/binomial2.PNG)
  - 독립시행이기 때문에 Var를 구할 때 공분산은 0으로 계산된다.
- 시행횟수 n, 성공확률 p인 이항분포의 확률질량함수  
![](/assets/images/statistics/binomial3.PNG)
  - n과 p에 따라 확률이 달라짐  
  => 이항분포의 모양을 결정  
  => 분포의 특성을 완전히 결정하는 값: 모수(parameter)
-  X~B(n,p) n : 실험횟수, p : 성공확률  
![](/assets/images/statistics/binomial4.PNG)




> 사진과 글은 KMOOC 사이트에서 숙명여대의 여인권 교수님의 [통계학의 이해1] 수업자료를 바탕으로 했습니다.  
