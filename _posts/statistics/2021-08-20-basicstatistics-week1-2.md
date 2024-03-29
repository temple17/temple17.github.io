---
title: KMOOC 통계학의 이해1 1주차-2
date: 2021-08-18 12:25:00
toc: true
toc_sticky: true
categories: statistics
tags:
  - KMOOC
---

# 확률표본추출 vs. 비확률표본추출

## 확률표본추출(Probability sampling)

- 모집단을 구성하는 모든 추출단위에 대해 표본으로 추출된 확률을 알 수 있는 추출법  
- 표본추출틀(sampling frame, 표집틀 필요)
- 특정한 표본이 선정될 확률을 토대로 추정오차를 확률개념을 이용하여 과학적으로 설명


### 단순확률추출법(SRS, Simple random sampling)
- 크기가 N인 모집단에서 크기 n인 표본을 무작위로 추출
- 모든 단위들의 표본에 선택될 확률이 동일
-- 실제 대규모 조사에서는 거의 사용되지 않지만 다른 모든 표본추출방법의 기초 이론

### 계통추출법(Systematic sampling)
- 표집틀에서 처음 1~k 번째 단위들 중 하나를 랜덤하게 선택한 다음, 매 k번째에 해당되는 단위들을 표본으로 추출
- 계통표본 추출과정
  - 추출간격 k의 결정 : N/n 또는 정확도를 고려 결정
  - 1~k에서 난수 하나를 선택해서 시작점을 선정
  - 시작점에 k를 반복적으로 더해서 표본추출
- 표집틀이 없어 고유번호 부여, 난수발생 등 단순확률추출법을 적용하기 어려운 실제 조사현장에서 폭 넓게 활용

### 층화추출법(Stratified random sampling)
- 모집단을 서로 중복되지 않는 여러 개의 층(strata)로 나누고, 각 층에서 단순확률추출에 의해 표본을 추출
  - 부모집단(subpopulation)의 구성 내역을 알고 있음
  - 부모집단 간 특성에 차이가 있음
  - 전체 모집단 크기 N, i번째 층의 크기 Ni, Wi = Ni/N
- 층화 표본추출 과정
  - 층의 구성(성별, 연령, 지역 등)
  - 각 층에서 독립적으로 표본 추출(단순확률 추출 사용)

### 집락추출법(Cluster sampling)
- 서로 인접한 조사단위들을 묶어 구성한 집락(cluster)을 추출하고, 이들 집락 내의 조사단위들을 조사
  - 예 : 서울시 고등학생 월평균 사교육비 추정
    - SRS :  
    추출틀 : 서울시 전체 고등학생명단 => 작성비용 과다  
    조사대상 : 서울 전역에 산재 => 조사비용 과다

    - 집락추출 :
    1단계 : 고등학교추출(PSU, primary sampling unit)  
    2단계 : 학생추출(학급->학생)

- 활용이유
  - 상대적으로 집락에 대한 표집틀 확보가 용이함
  - 산재되어 있는 조사단위들에 대한 관측비용을 감소시킬 수 있음

***
## 비확률표본추출(non-probability sampling)

- 특정 표본이 선정될 확률을 알 수 없음 => 추론과의 정확도를 알 수 없다.

### 편의추출 : 자발적 참여, 백화점 앞, 포털 사이트 인터넷 조사
### 유의추출 : 전문가 선택  
### 할당추출 : 그룹 내 조사대상 선택에서 랜덤화 과정 없음
### 간편하고 비용이 적게 든다는 이유로 사회조사에서 광범위하게 사용됨  


***
# 목표모집단 vs. 조사모집단

## 목표모집단(target population)
- 관심대상이 되는 모든 기본단위들의 집합
- 시공간상 명확하게 정의된 연구 대상 집단
    - 조사시점, 지리적인 경계, 연령 기준 등

## 조사모집단(survey population)
- 조사가능모집단(accessible population)
- 표본추출 대상 기본단위들의 집합
- 표본추출틀을 통해 추출될 수 있는 기본단위들의 집합
  - 예 : 전화여론조사 : 전화번호부(표본추출틀)에 등재된 전화보유 가구의 성인


> 사진과 글은 KMOOC 사이트에서 숙명여대의 여인권 교수님의 [통계학의 이해1] 수업자료를 바탕으로 했습니다.  
