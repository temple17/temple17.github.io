---
title: KMOOC 기초통계 10주차-2
date: 2021-09-07 12:25:00
toc: true
toc_sticky: true
categories: statistics
tags:
  - KMOOC
---

# 음이항분포

## 기하분포(Geometric Distribution)

- 성공할 확률이 p인 베르누이 시행을 성공할 때 까지 시행하는 경우 실패(시행)횟수의 분포
  - 표본 공간 : S,FS,FFS,FFFS,...
  - X ~ Geo(p)
  - 제 1항이 p이고 공비가 1-p인 등비급수 형태
  - Y = X+1 : 시행 횟수
![](/assets/images/statistics/geometric.PNG)   
- 무기억성(memoryless) : 앞에 시행에 대해 전혀 기억하지 않음
  - 5번 연속 뒷면이 나왔다고 하더라도 6번째가 앞면일 확률은 0.5

### 기댓값   
![](/assets/images/statistics/geometric2.PNG)   

## 음이항분포(Negative Binomial Distribution)
- 성공할 확률이 p인 베르누이 시행을 r번 성공할 때까지 시행하는 경우 실패(시행)횟수의 분포
- X : 실패횟수, Y : 시행횟수(Y=X+r)
- Y = y라고 하면, y번째는 S
  - y-1번째까지 결과:r-1개, y-r개 F    
  ![](/assets/images/statistics/negative.PNG)   
  - Y ~ NB(r,p)

### 기댓값
  ![](/assets/images/statistics/negative2.PNG)   


> 사진과 글은 KMOOC 사이트에서 숙명여대의 여인권 교수님의 [통계학의 이해1] 수업자료를 바탕으로 했습니다.  