---
layout: post
title: "블록 체인의 개념"
categories: BlockChain
author: bn-tw2020
---
* content
{:toc}


## 블록체인

블록체인에서 비디오 영상을 판매할 수 있다.  
처음 보는 사람은 무슨 소리인지 이해가 가지 않을 것이다.  
어떻게 블록체인에서 비디오 영상을 판매하지? 라는 궁금증이 생길 것이다.  





```
블록체인은 빗코, 이더, 에이다, 리플 ... 등등을 돌아가게하는 기반이다.
블록체인(BlockChain) = 블록(Block) + 체인(Chain)
  (블록체인 = 블록들이 모여있는 체인)

좀 더 쉽게 이해하기 위해서 블록(block)이라는 단어를 데이터베이스(database)로 생각해보자.
블록체인은 신기하고 좋은 데이터베이스이다.

why?

* 더하기(append)만 가능하기 때문이다.
  즉, 추가만 가능하고 삭제는 안됩니다. 편집도 안되고. 오로지 추가만 가능하게 되는 것이다.

    Example)
    1. 대학교 학위의 블록체인이라고 생각을해보면, 
       사용자의 대학교 학위는 블록체인에 추가 되고, 절대 편집/삭제되지 않는다.

    2. 정부는 운전면허증이라든지, 지원금 사용내역 등을 기록할 수 있다.

    3. 사람들이 자신의 전세계약서 같은 것들을 보관하면,
       그 누구도 삭제할 수 없고, 그대로 잘 보관할 수 있다.

* 탈중화(Decentralization)
  블록체인은 탈중화가 가능하다.
  
  "탈중앙화"는 특정 개인이 DB를 관리할 수 없다는 뜻이다.
  모두가 DB의 복제본을 가지고 있다.

  "만약 내가 2천만 이더를 갖고 있다."라고 거짓말을 하면,
  다들 DB복제본을 가지고 있기 때문에. 이 거짓말을 통할 수 가 없다.
즉, 이것이 분산화된 DB라고 할 수 있는 것이다.
  
  많은 사람들이 비트코인 노드를 돌리고 있으며, 우리 모두가 정확하게 동일한 DB복제본을 갖고 있고
우리 모두가 컴퓨터를 몽땅 끄고 해야 비트코인이 죽을 수 있다.
하지만, 일어날 수 없는 일입니다. 전세계 모두가 동시에 그렇게 행동할 수 없기 때문이다.

이러한 이유로 매력적인 데이터베이스라고 부를 수 있는 것이다.
```

## 블록

블록이 정보를 DB에 추가하는 방법이다.  
데이터를 그냥 적어서 추가하는 것이 아니라 `블록`이라는 것을 추가한다.  

<img width="514" alt="스크린샷 2021-03-09 오후 2 01 59" src="https://user-images.githubusercontent.com/66770613/110421050-06337f80-80e0-11eb-854c-6149cf7132c8.png">

```
블록에는 중요한 정보들이 많다.
    1. "블록의 해시'
    2. "이전 블록의 해시"
    3. "데이터"


데이터
  블록체인은 위에서 설명하듯이 그 무엇이든의 DB이다. (결혼증명서, 운전면허증 ... 혹은 대학교 학위 ...)
  데이터라고 말한 부분에 (결혼증명서, 운전면허증 ... 혹은 대학교 학위 ...) 넣는 것이다.
  
  비트코인의 경우에는 그 데이터는 '트랜잭션(거래내역)'이 된다.(누가 얼마나 있고, 누구에게 얼마나 보냈고..)


해시
  해시는 수학 함수이며, 한개의 input을 받으면, output을 준다.
  일방향 함수이고 결정론적이다.
  결정론적: input '사랑해'의 output은 항상 같은 것으로 정해져있다는 것이다.
                '사랑해!'라고하면 '사랑해'의 output과 완전히 다르게 보일 것이다.
  일방향함수: input으로 output을 구할 수 있지만, output으로는 input을 구할 수 없는 것이다.
           사과를 사과쥬스로 만들 수 있지만, 사과쥬스로 사과를 만들 순 없는 거랑 비슷합니다.


해시가 중요한 이유는 블록들이 서로 연결된 방법이기 때문이다. 이것이 체인을 만들기 때문이다.

Q. 나 자신을 블록이라고 생각하고 빗코 블록체인에 추가되고 싶다고하면?

먼저, 결제 내역들을 모아서 내 주머니에 넣자. (데이터 부분)
다음, 내 주머니에 이전 블록의 해시를 넣는다. 
다음, 나의 데이터 + 이전 블록의 해시를 합쳐서 다시 해시를 한다. ⟹ 나만의 해시가 생긴다!!
이제 블록체인에 블록을 추가할 수 있다.

!! 모두가 이전 해시랑 같이 결합을 한다는 것이다.
   이와 같은 방법으로 체인이 결성되는 것이다.

   if) 블록체인이 천만개의 블록을 갖고 있다면,
       누군가 1번 블록에서 1을 0으로 바꾼다면 혹은 0을 1로 바꾼다면?
       모든 해시들도 몽땅 바뀐다. 해시의 특징때문이다.
       이 방법으로 체인이 연결되고 덕분에 누구도 블록체인 변경을 할 수 없는 것이다.
```