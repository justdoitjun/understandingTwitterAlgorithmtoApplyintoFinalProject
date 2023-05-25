# Purpose : to understand main logics(not wholly) to apply it into final Project partially. 
Applying Twitter-recommendation algorithm into final Projects. 

To read
https://github.com/twitter/the-algorithm/blob/main/cr-mixer/server/src/main/scala/com/twitter/cr_mixer/model/Candidate.scala#L161
https://github.com/twitter/the-algorithm/tree/main/src/scala/com/twitter/simclusters_v2




ETA : 2 days to understand whole logics. 

![image](https://github.com/justdoitjun/finalProject/assets/119689162/76c4a3b3-18de-42dc-ba08-85ab529f9241)

<img width="1440" alt="image" src="https://github.com/justdoitjun/finalProject/assets/119689162/0a05b247-f02d-44d6-8c44-a378e4fa5f91">


## Search Index => so called " Early bird System " 
> https://github.com/twitter/the-algorithm/tree/main/src/java/com/twitter/search

![image](https://github.com/justdoitjun/understandingTwitterAlgorithmtoApplyintoFinalProject/assets/119689162/ea2325eb-3828-4afc-ba09-0b974fc2f472)


(1) "search-index" comprise 50% of tweets. -> We call it as 'early bird' in Twitter

How it works? -> By 'search Index'. 
Given a list of following users, find their recently posted tweets. 
For example, suppose user A follows user B and user C. Since user B posted lately posts, Twitter put weights on user B. 

Search Index => three clusters. 
(1) a realtime cluster (2) a protected clsuter (3) archive cluster

a realtime cluter -> 7 days
a protected clsuter -> indexing all protected tweets for the same timeframe
an archive cluseter -> 2 days


![image](https://github.com/justdoitjun/understandingTwitterAlgorithmtoApplyintoFinalProject/assets/119689162/baad4805-0923-4d3f-82ca-a072d2549724)




### Search Index => 

https://github.com/twitter/the-algorithm/blob/main/src/java/com/twitter/search/core/earlybird/README.md




### 클러스터링은 필수 중 필수
* 학부 때 들었던 선형대수랑 3Blue1Brown을 다시 들어서 이해해봐야겠다. 
> 신기한 점은 선형대수를 사용한다는 점임. 
> 정보의 Producer가 있고, 정보의 producer간 관계를 cosine식으로 상수화해두고, 이 둘간의 조합을 통해서, 

결국은 
![image](https://github.com/justdoitjun/understandingTwitterAlgorithmtoApplyintoFinalProject/assets/119689162/f6e438a7-170c-4ed4-9f69-6919f994f0bb)

배경지식
<img width="821" alt="image" src="https://github.com/justdoitjun/understandingTwitterAlgorithmtoApplyintoFinalProject/assets/119689162/a9d766e0-f713-4749-93c8-bc87f75c4e9d">


학부 때 배웠던 코사인 유사도를 생각해보자. 기본 정의는 다음과 같고, 핵심은 두 벡터값이 roughly 동일한(유사한) 방향을 얼마나 pointing하고 있느냐에 대한 것이다. 
즉, 코사인 

이 공식을 굳이 왜 찾아봤냐면, 나머지 유사도에 대해서는 직관적으로 이해가 되는데 cosine(v2, v4) = 0.7은 이해가 안되어서 봤다. 얼핏 직관적으로 보기엔 cosine(v1, v4) 와 비슷해보이는데 0.5가 아닌가라고 추론해볼 수 있기 때문이다. 하지만, 위의 정의대로 계산해보면 0.7이 맞다.  
![producer_producer_similarity](https://github.com/justdoitjun/understandingTwitterAlgorithmtoApplyintoFinalProject/assets/119689162/acd15b03-0a1c-40f2-9e95-222e0cd20b62)
cosine(v2, v4) = 0.7이라는 것이 직관적으로 보이지는 않을텐데
분자 = 1
분모 = 루트2 * 루트1 
울프람에 계산을 해보면
![BB1BB465-34F3-459F-B1FF-66F95208CE90](https://github.com/justdoitjun/understandingTwitterAlgorithmtoApplyintoFinalProject/assets/119689162/3ac38b2c-00b1-4939-9ef5-2b25cccbb073)



![image](https://github.com/justdoitjun/understandingTwitterAlgorithmtoApplyintoFinalProject/assets/119689162/d3d8fe60-7b1e-48fb-8b7c-1b7fc46c3e24)


![image](https://github.com/justdoitjun/understandingTwitterAlgorithmtoApplyintoFinalProject/assets/119689162/a539a175-05b6-477c-bf13-f908ee2f814b)


![image](https://github.com/justdoitjun/understandingTwitterAlgorithmtoApplyintoFinalProject/assets/119689162/3104882e-c470-4fe9-a751-31b88b3ddff3)




https://www.youtube.com/watch?v=kYB8IZa5AuE&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=3
