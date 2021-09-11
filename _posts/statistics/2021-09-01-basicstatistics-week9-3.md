---
title: KMOOC 기초통계 9주차-3
date: 2021-09-01 12:25:00
toc: true
toc_sticky: true
categories: statistics
tags:
  - KMOOC
---

# 초기하분포(Hypergeometric Distribution)


- 크기가 N인 모집단이 크기가 M과 N-M인 두개의 부모집단(A,B)로 나누어진 경우 => 유한모집단
- n개의 표본을 비복원으로 추출할 때, 부모집단(A)에서 추출될 표본 수의 분포   
=> 각 표본의 추출과정을 독립적이지 않음

## 확률질량함수 일반식:
![](/assets/images/statistics/hypergeo.PNG)
- N이 크고 N에 비해 n이 상대적으로 작은 경우
  - 비복원의 효과가 적기 때문에 베르누이 실험으로 근사
  - 초기하분포는 p = M/N인 이분항분포로 근사

### 기댓값
- 초기하분포도 각 시행에서 A 집단에서 추출되면 1,  
다른 집단에서 추출되면 0으로 표시한 확률변수의 합  
![](/assets/images/statistics/hypergeo2.PNG)
- 그러나 베르누이와 다르게, 독립시행이 아니기 때문에, 확률은 동일하다.

![](/assets/images/statistics/hypergeo3.PNG)  

***

![](/assets/images/statistics/hypergeo4.PNG)

***

![](/assets/images/statistics/hypergeo5.PNG)

## 품질관리 - Operating Characteristic(OC) curve
- 초기하분포를 활용한다.
- 50개의 전구들이 들어 있는 상자에서 10개의 전구를 무작위로 선택하여 검사
- 불량전구의 개수가 1개 이하이면 이 회사의 전구를 구매
- 만약 이 상자에 5개의 불량품이 있을 때, 구매할 확률은?
  - X = 10개 중 불량품의 수  
![](/assets/images/statistics/hypergeo6.PNG)

***

![](/assets/images/statistics/hypergeo7.PNG)

- OC curve 계산 고려사항
  - 몇 개의 표본을 추출할 것인가?
  - 불량품이 몇 개일 때 까지 구매할 것인가?

## 연못에 사는 물고기는 몇 마리?
- 꼬리표를 붙인 20마리의 물고기를 연못에 넣고 어느 정도 지난 후  
 물고기 15마리를 잡았을 때 꼬리표가 있는 물고기의 분포는?
  - N-20 : 꼬리표가 없는 물고기
- 15마리 중 4마리가 꼬리표가 있는 물고기라면?
  - 비례식 : N = 75
  - 비례식을 이용해서 N을 구할 수 있다.



> 사진과 글은 KMOOC 사이트에서 숙명여대의 여인권 교수님의 [통계학의 이해1] 수업자료를 바탕으로 했습니다.  
