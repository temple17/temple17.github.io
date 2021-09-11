---
title: KMOOC 기초통계 3주차-5
date: 2021-08-20 12:25:00
toc: true
toc_sticky: true
categories: statistics
tags:
  - KMOOC
---

# 수치자료의 형태

많은 통계분석 방법은 모집단이 중심위치를 기준으로 대칭이라고 가정

## 왜도(skewness)
- 자료가 대칭적으로 분포되어 있는지, 한쪽으로 기울어져 있는지에 대한 측도  
![](/assets/images/statistics/skewness.jpg)
- 피어슨(Karl Pearson) 제안

![](./assets/images/statistics/skewness2.PNG)  


![](./assets/images/statistics/skewness3.PNG)  

- 오른쪽 꼬리가 길면 큰 양수값을 가짐(양의 왜도 <-> 음의 왜도)

- 수정된 왜도  
![](/assets/images/statistics/skewness4.PNG)  

## 첨도(kurtosis)
- 양쪽꼬리가 얼마나 두터운지를 나타내는 값  
![](/assets/images/statistics/kurtosis.jpg)    

- 피어슨(Karl Pearson) 제안  
![](/assets/images/statistics/kurtosis2.PNG)   
![](/assets/images/statistics/kurtosis3.PNG)   

- 정규분포의 경우 이론적으로 첨도는 3
- 수정된 첨도  
![](/assets/images/statistics/kurtosis4.PNG)   

### 왜도 & 첨도의 활용
- 자료 분포의 형태를 나타내는 측도
- 심한 왜도를 가지거나 큰 첨도를 가지는 경우  
=> 자료에 이상점이 있을 가능성이 높아짐

- 정규성 검정
  - 왜도 = 0, 첨도 = 3이 아니라면?
    - Jacque-Bera 검정  
    ![](/assets/images/statistics/jacque.PNG)   


> 사진과 글은 KMOOC 사이트에서 숙명여대의 여인권 교수님의 [통계학의 이해1] 수업자료를 바탕으로 했습니다.  

