# 알고리즘
[Ch 01-3. 추천 알고리즘의 종류](https://velog.io/@hyxxnii/Ch-03.-%EC%B6%94%EC%B2%9C-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98%EC%9D%98-%EC%A2%85%EB%A5%98)

[갈아먹는 추천 알고리즘 1 추천 알고리즘의 종류](https://yeomko.tistory.com/3)

> 원칙  
> 1. Source 분류  
> 2. Source 내에서 rank   
> 3. 휴리스틱과 필터   

> * 추천 알고리즘:   
> 아이템 Pool(전체) > 특정 후보군 생성 > 후보군 바탕으로 Intentions or Filtering > Ranking  


<1> Cluster - Source 분류 = 특정 후보군 생성
나는 총 3가지 후보군을 제시할 예정. 

0. 광고 : 만약 매물이 잘 나가지 않은 host의 경우에는 host가 거래 성사시 15%의 지분만 공유한다면, suggestion에 광고를 올린다. 이 광고는 딱 1건의 host만 제시해준다. 
1. 절반 : 내가 찜한(팔로우한) 매물을 우선적으로 보여줌. In-Network Source
2. 절반 : 내가 찜한(팔로우하지 않은) 매물을 차선으로 보여줌. Out-of-Network Source

(1) Social Graph : Our first approach is to estimate what you would find relevant by analyzing the engagements of people you follow or who have similar interests. 
* (1) - 1. Search-Index
-> 한 매물에 대해 좋아요를 누른 사람들의 interest를 분류하고 그 interests 들을 공통적으로 많이 보유하고 있는 사람들의 매물들을 clustering하라
즉, A가 알파라는 매물에 대해 좋아요를 눌렀다면, 알파라는 매물을 좋아요한 사람들의 interests를 분류하고, 그 집단의 사람들이 어떤 매물들을 가장 많이 좋아요했는지를 확인해보자. 


- - - -
- - - -

* (1) - 2. CR-Mixer
-> 비슷한 성향을 가진 집단 생성하고, 
-> Cluster를 하기 위해서는 통계와 머신러닝이 필요합니다. 
몇가지 가정 : 모집단이 정규분포를 따른다. 
* 통계적 집단성을 나타나기 위해서는 
<관심사에 대한 가중치 : heurisitc>
* 직접적인 관심사 설정: 가중치 40
* 실제 찜(Likes) 관심사 : 가중치 20
* 클릭 로그기록 : 가중치 5
-> 항목을 더 많이 클릭할수록, Likes에 넣을수록, 


> 결국 핵심은 이 식임.   

- 정보이용자에게 적합한 Community 추천 -> 
이 Community는 2가지 요소에 의해 결정된다. 
첫째, Consumer - Producers 
둘째, Producers - Communities 
-> Proudcers가 모두 동일하기 때문에 Consumers - Communities로만 구성된다. 

![](Algorithm101(May24)/interestedin.png)

![](Algorithm101(May24)/bipartite_graph.png)




- - - -
- - - -


## Community Detection - Known For

Fundamental understanding
[Cosine Similarity - an overview | ScienceDirect Topics](https://www.sciencedirect.com/topics/computer-science/cosine-similarity)
It is a gist and ground to understand linear combination and how twitter recommend users. 
Briefly saying, 


* 코사인 유사도 
Cosine similarity : => Gist : It is often used to measure document similarity in text analysis.
-> Whether two vectors are pointing in roughly the same direction. $$$$

Cosine similarity measures the similarity between two vectors of an inner product space. - By definition

It is measured by the cosine of the angle between two vectors and determines whether two vectors are pointing in roughly the same direction.
![](Algorithm101(May24)/7046153F-23A4-4779-9BB6-53EB8BED64BD.png)

이 공식을 굳이 왜 찾아봤냐면, 나머지 유사도에 대해서는 직관적으로 이해가 되는데 cosine(v2, v4) = 0.7은 이해가 안되어서 봤다. 얼핏 직관적으로 보기엔 cosine(v1, v4) 와 비슷해보이는데 0.5가 아닌가라고 추론해볼 수 있기 때문이다. 하지만, 위의 정의대로 계산해보면 0.7이 맞다.  울프람에서 계산한 걸 보면
![](Algorithm101(May24)/producer_producer_similarity.png)


cosine(v2, v4) = 0.7이라는 것이 직관적으로 보이지는 않을텐데
분자 = 1
분모 = 루트2 * 루트1 

![](Algorithm101(May24)/BB1BB465-34F3-459F-B1FF-66F95208CE90.png)




> 정보 이용자(Consumer)와 정보 생산자(Producers)간의 상관관계를 만들어내고,  정보이용자(팔로워)가 누군가(Producers)를 팔로우하면, 이 관계각 cosine관계식으로 분류가 된다. cosine(v1, v2) 가 여기서 나오는 거 같음.   
Producer-producer similarity is computed as the cosine similarity between users who follow each producer. 

![](Algorithm101(May24)/producer_producer_similarity.png)

![](Algorithm101(May24)/knownfor.png)



![](Algorithm101(May24)/producer_embeddings.png)

![](Algorithm101(May24)/topic_embeddings.png)



<2> Source 내에서 Ranking
0. 광고 : 1개만























<화면구성>
여행을 떠날 시간입니다. 
Suggestions
- 회원님이 찜한 목록을 기반으로한 List + 찜하지는 않았지만 좋아하는 클러스터를 기반으로한 List 















