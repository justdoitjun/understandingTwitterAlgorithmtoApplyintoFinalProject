# Purpsoe : to understand main logics(not wholly) to apply it into final Project partially. 
Applying Twitter-recommendation algorithm into final Projects. 

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

