---
title: Netflix Movies and TV Shows (2) Top 10 countries on Netflix
date: 2022-07-19 12:25:00
categories: kaggle
tags:
  - kaggle
  - netflix
---

> 해당 그래프와 코드는 [Josh's notebook](https://www.kaggle.com/code/joshuaswords/netflix-data-visualization)을 참고한 것임을 밝힙니다.   
> 해당 노트북은 [안수빈님의 notebook](https://www.kaggle.com/code/subinium/awesome-visualization-with-titanic-dataset)에서 다양한 디자인 기법에서 영감을 받은 것으로 Netflix의 brand palette와 Insight를 결합한 visualization을
> 구현했다는 점에서 공부할 가치가 충분히 있다고 생각합니다.


# 1. Top 10 countries on Netflix
첫번째 그래프는 type(영화, 방송)에 구분 없이 가장 많은 콘텐츠를 생산하고 있는 상위 10개의 국가를 나타낸 그래프입니다.
![](/assets/images/netflix/top%2010%20countries%20on%20netflix.PNG)
이 그래프를 일정한 단계로 끊어서 build 해보겠습니다.

## 1.1 Netflix brand color
~~~python
sns.palplot(['#fafafa', '#4a4a4a', '#e3120b'])
plt.title('Netfilx brand palette', loc = 'left', fontfamily='serif', fontsize=15, y=1.2)
~~~
![](/assets/images/netflix/netflix palplot.PNG)

## 1.2 Top 10 countries' colors
~~~python
color_map = ['#f5f5f1' for _ in range(10)]
color_map[0] = color_map[1] = color_map[2] = '#e3120b'
~~~
상위 10개 국가를 나타내기 위해서 기본적으로 10개의 bar를 모두 #f5f5f1 색으로 지정하고   
상위 3개의 국가는 넷플릭스의 대표 색으로 지정합니다.

## 1.3 순서대로 그래프 그리기

### 1.3.1 
~~~python
fig, ax = plt.subplots(1, 1, figsize=(12,6))
ax.bar(data.index, data, width=0.5, edgecolor='darkgrey', linewidth = 0.6, color = color_map)
~~~
![](/assets/images/netflix/131.PNG)
- 가장 기본적인 barplot입니다.

### 1.3.2
~~~python
for i in data.index:
    ax.annotate(f"{data[i]}",
                xy=(i, data[i]+150),
                va='center', ha='center', fontweight='light',fontfamily='serif')
    
for s in ['top', 'left','right']:
    ax.spines[s].set_visible(False)
~~~
![](/assets/images/netflix/132.PNG)
- `ax.annotate` 함수를 통해 각각의 bar위에 annotation을 표기해줍니다.
- top, left, right 의 axis를 제거해줍니다.

### 1.3.3
~~~python
ax.set_xticklabels(data.index, fontfamily = 'serif', rotation=0)

fig.text(0.09, 1, 'Top 10 countries on Netflix', fontsize=15, fontweight='bold', fontfamily='serif')
fig.text(0.09, 0.95, 'The three most frequent countries bave been highlighted', fontsize=12, fontweight='light', fontfamily='serif')

fig.text(1.1, 1.01, 'Insight', fontsize=15, fontweight='bold', fontfamily='serif')

fig.text(1.1, 0.67, '''
The most prolific producers of
content for Netflix are, primarily,
the USA, with India and the UK
a significant distance behind.

It makes sense that the USA produces 
the most content as, afterall, 
Netflix is a US company
''', fontsize=12, fontweight='light', fontfamily='serif')
~~~
![](/assets/images/netflix/133.PNG)
- xticklabel의 글꼴을 serif로 변환해줍니다.
- fig.text함수는 plot 내에 글자를 삽입할 수 있도록 합니다.
- (0, 0)은 왼쪽 아래, (1, 1)은 오른쪽 위를 나타냅니다.

### 1.3.4
~~~python
ax.grid(axis='y', linestyle='-', alpha=0.4)
grid_y_ticks= np.arange(0, 5000, 500)
ax.set_yticks(grid_y_ticks)
ax.set_axisbelow(True)

plt.axhline(y=0, color='black', linewidth=1.3, alpha=.7)

ax.tick_params(axis='both', which='major', labelsize=12)
~~~
![](/assets/images/netflix/134.PNG)
- y축의 눈금을 기준으로 grid를 그려줍니다.
- `set_yticks`를 이용해서 y축 범위를 0~4500을 500씩 끊어줍니다.
- 보조선이 아래쪽에 위치할 수 있도록 True값을 지정해줍니다.
- `axhline`은 x axis의 line style을 지정해줍니다. 더 두껍고, 더 어둡게 설정해서 이전 그래프보다 눈에 띄도록 합니다.
- `tick_params`는 minor인 경우, major label 사이사이에 보조 label이 들어가도록 하는데 이 그래프에서는 major만 사용하도록 합니다.

### 1.3.5
~~~python
import matplotlib.lines as lines

l1 = lines.Line2D([1,1],[1, 0], transform = fig.transFigure, figure=fig, color='black', lw=0.2)

fig.lines.extend([l1])

ax.tick_params(axis=u'both', which=u'both', length=0)

plt.savefig('top10 countries on netflix.png')
~~~
![](/assets/images/netflix/top%2010%20countries%20on%20netflix.PNG)
- `fig.transFigure`의 경우 앞서 (0,0)은 왼쪽 아래, (1,1)은 오른쪽 위를 나타냈는데
- 이에 맞춰 1,1 에서 1,0 으로 내려가는 직선을 그려줍니다.
- line을 선언하고, extend 함수로 그려줍니다.
- `ax.tick_params`를 이용해서 xtick과 ytick에 작게 남아있던 눈금을 지워줍니다.

### 전체 코드
~~~python
fig, ax = plt.subplots(1, 1, figsize=(12,6))
ax.bar(data.index, data, width=0.5, edgecolor='darkgrey', linewidth = 0.6, color = color_map)

for i in data.index:
    ax.annotate(f"{data[i]}",
                xy=(i, data[i]+150),
                va='center', ha='center', fontweight='light',fontfamily='serif')
    
for s in ['top', 'left','right']:
    ax.spines[s].set_visible(False)

ax.set_xticklabels(data.index, fontfamily = 'serif', rotation=0)

fig.text(0.09, 1, 'Top 10 countries on Netflix', fontsize=15, fontweight='bold', fontfamily='serif')
fig.text(0.09, 0.95, 'The three most frequent countries bave been highlighted', fontsize=12, fontweight='light', fontfamily='serif')

fig.text(1.1, 1.01, 'Insight', fontsize=15, fontweight='bold', fontfamily='serif')

fig.text(1.1, 0.67, '''
The most prolific producers of
content for Netflix are, primarily,
the USA, with India and the UK
a significant distance behind.

It makes sense that the USA produces 
the most content as, afterall, 
Netflix is a US company
''', fontsize=12, fontweight='light', fontfamily='serif')

ax.grid(axis='y', linestyle='-', alpha=0.4)
grid_y_ticks= np.arange(0, 5000, 500)
ax.set_yticks(grid_y_ticks)
ax.set_axisbelow(True)

plt.axhline(y=0, color='black', linewidth=1.3, alpha=.7)

ax.tick_params(axis='both', which='both', labelsize=12)

import matplotlib.lines as lines

l1 = lines.Line2D([1,1], [1, 0],transform = fig.transFigure, figure=fig, color='black', lw=0.2)

fig.lines.extend([l1])

ax.tick_params(axis=u'both', which=u'both', length=0)

plt.savefig('top10 countries on netflix.png')
~~~

# 개인적인 Insight
- 콘텐츠 소비가 가장 많은 나라 10개국을 확인했지만, 그에 따른 수익성과 MAU와 같은   
활성 지표를 확인한다면 좋을 것 같습니다. 그만큼 콘텐츠 제작에 더 많은 투자비용이 들어가지만
만약 이 투자 비용을 회수하는 것 이상으로 이윤을 창출하거나 유저들에게 영향력을 줄 수 없다면   
어떤 장르 혹은 작품에 집중해야 할 것인지 니즈를 파악할 수 있을 것입니다.  
- 또한, 이는 4위부터 10위 사이의 나라들 중 투자를 더 과감하게 해야 할 시장이 어디인지를 나타낼 수 있을 것입니다.   
작품의 수는 적을 수 있지만, 그 안에서의 여러 지표들을 확인하고 긍정적인 반응을 확인할 수 있다면 새로운 투자국가로 여길 수 있을 것입니다.    
실제로 최근 경제 침체를 비롯하여 다수의 유저 유출로 인한 실적 부진으로 넷플릭스의 주가는   
급격하게 하락했고, 700달러대까지 치솟던 주가는 현재 200달러 초반을 유지하고 있습니다.    
데이터라는 것이 전체적인 지표와 상황을 확인하기에 매우 용이하고 핸들링하기 좋지만 결국엔 그 비즈니스의 근본과 수치화할 수 없는 창작물의 질이 중요한 요소라는 사실을 깨닫게 됩니다. 
이러한 거시적인 관점을 가진다면 유저의 클릭과 시청횟수 등을 높일 수 있도록 기여하는 머신러닝 알고리즘의 성능도 높여야 할 것이며 디자인, 콘텐츠, 출시 시기 등 여러 상세 요소의 결합으로 더 강력한 기업이 되지 않을까 싶습니다.

> 다음으로 Top 10 countries의 영화와 방송 비율을 horizontal bar chart로 나타내는 것을 상세하게 살펴보겠습니다.

# 2. Top 10 countries Movie & TV Show split
![](/assets/images/netflix/top10%20countries%20movie%20&%20tv%20show%20split.png)

# 업로드 주소
해당 주피터 노트북은 [여기](https://github.com/temple17/kagglepractice/blob/main/Netflix_Movies_and_TV_Shows.ipynb)에     
지속적으로 업데이트 할 예정이니 전체 코드가 궁금하신 분들은 확인해주세요.   

*Just do it & Keep steady*
