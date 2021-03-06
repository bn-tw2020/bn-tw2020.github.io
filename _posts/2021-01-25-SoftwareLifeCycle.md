---
layout: post
title: "소프트웨어 생명 주기"
categories: 소프트웨어공학
author: bn-tw2020
---
* content
{:toc}

## 소프트웨어 생명 주기

```
소프트웨어 생명 주기는 소프트웨어 개발 방법론의 바탕이 되는 것으로, 
소프트웨어를 개발하기 위해 정의하고 운용, 유지보수 등의 과정을 각 단계별로 나눈 것이다.
```




---

## 소프트웨어 생명 주기 모형

### 폭포수 모델 (Waterfall)

```
1. 폭포에서 한 번 떨어진 물은 거슬러 올라갈 수 없듯이
   소프트웨어 개발도 이전 단계로 돌아갈 수 없다는 전제하에 각 단계를 확실히 매듭짓고 그 결과를 철절하게
   검토하여 승인 과정을 거친 후에 다음 단계로 진행하는 개방 방법론

2. 타당성 검토 > 계획 > 요구분석 > 설계 > 구현 > 테스트 > 유지보수 단계로 이루ㅇ어져있다.
```

### 프로토타입 (Prototype)

```
1. 사용자의 요구사항을 정확히 파악하기 위해 실제 개발될 소프트웨어에 대한 견본을 만들어 최종 결과물을 예측하는 모형
2. 폭포수 모형은 개발이 완료된 시점에서 오류가 발견되는 현상이 발생하는데 이것을 보완한 모형이다.
3. 요구사항이 불분명할 경우 사용하여 좋다.
```

### 나선형 모형 (Spiral)

```
1. 계획 및 정의 > 위험 분석 > 공학적 개발 > 고객 평가
2. 폭포수 모형 + 프로토 타입의 장점에 위험 분석 기능을 추가한 모형
3. 간단하게, 나선을 따라 돌듯이 여러 번의 소프트웨어 개발 과정을 거쳐 점진적으로 완벽하게 개발하자라는 것이다.
4. 개발하면서 발생할 수 있는 위험을 관리하고 최소화하는 것이 목적이다.
```

### 애자일 모형

```
1. 애자일은 `민첩함` `기민한`이라는 의미로,
2. 고객의 요구사항 변화에 유연하게 대응할 수 있도록 일정한 주기를 반복하면서 개발과정을 진행한다.
3. 스프린트 or 이터레이션이라고 불리는 짧은 개발 주기를 반복하며, 주기마다의 결과물에 대한 고객의 평가와 요구를 적극 수용한다.
4. 애자일 개발에서는 도구보다 개인과의 상호작용, 문서보다는 실행되는 S/W에 가치 두기, 계약 협상보단 고객과 협업, 계획보단 변화에 반응이라는 핵심가치가 존재한다.
5. 애자일 모형의 소프트웨어 개발 모형에는 스크럼, XP, 기능 중심 개발 ...이 존재한다.
```

#### 스크럼

스크럼은 팀원 스스로가 스크럼 팀을 구성하며, 개발 작업에 관한 모든 것을 스스로 해결해야 한다.  
스크럼 팀은 제품 책임자(PO), 스크럼 마스터(SM), 개발팀(DT)로 구성된다.  

* 제품 책임자
   이해관계자들 중 개발될 제품에 대한 이해도가 높고, 요구사항을 책임지고 의사 결정한 사람으로 선정한다.  
   의견을 종합하며, 요구사항을 작성하는 주체이다.  
   요구사항이 담긴 `백로그(Backlog)`를 작성하고 우선순위를 지정한다.  
   팀원들은 백로그에 스토리를 추가할 수 있지만, 우선순위 지정은 불가능

* 스크럼 마스터
   스크럼 팀이 스크럼을 잘 수행할 수 있도록 객관적인 시각에서 조언을 해주는 가이드 역할을 한다.  
   팀원들을 통제하는 것이 주 목표!  
   일일 스크럼 회의를 주관하여 진행 사항을 점검하고 장애 요소를 처리해야 한다.

* 개발팀
   위의 2명을 제외한 모든 팀원으로, 개발자 외에도 디자이너, 테스터 등 제품 개발에 참여하는 모든사람  
   약 7 ~ 8명의 구성으로 이룬다고 한다.

* 스크럼 개발 프로세스

```
1. 스프린트 계획 회의 > 스프린트 > 일일 스크럼 회의 > 스프린트 검토 회의 > 스프린트 회의
2. 제품 백로그은 모든 요구사항을 우선순위에 따라 나열한 목록이며, 새롭게 도출되는 요구사항이 추가된다.
3. 스프린트 계획 회의는 제품 백로그 중 이번 스프린트에서 수행할 작업을 대상으로 단기 일정을 수립하는 것
4. 스프린트는 실제 개발 작업을 진행하는 과정으로 2 ~ 4주 정도의 기간 내에서 진행한다.
5. 일일 스크럼 회의는 팀원들이 약속된 시간에 약 15분정도의 진행 상황을 점검하는 것이며, 소멸 차트를 이용한다.
6. 스프린트 검토 회의는 스프린트의 한 주당 한 시간 내에서 진행하며, PO는 개선할 사항을 정리하며
   다음 스프린트에서 반영할 수 있도록 제품 백로그에 업데이트 한다.
7. 스프린트 회고는 스프린트 주기를 되돌아 보며 정해놓은 규칙을 잘 했는지 확인하고 기록하는 것이다.
```
        
#### XP

XP(eXtreme Programming)는 수시로 발생하는 고객의 요구사항에 유연하게 대응하기 위해 고객의 참여와 개발 과정을 반복을 극대화하여 개발 생산성을 향시키는 방법이다.

* `짧고 반복적인 개발 주기` `단순한 설계` `고객의 적극적인 참여`
* 릴리즈의 기간을 짧게 반복하면서 고객의 요구사항 반영에 대한 가시성을 높인다. 고객이 릴리즈 테스트에 직접 참여!
* 핵심 가치로는 `단순성` `의사소통` `피드백` `존중` `용기`

* XP 개발 프로세스

```
1. 사용자 스토리 > 릴리즈 계획 수립 > 주기 > 승인 검사 > 소규모 릴리즈
2. 사용자 스토리는 고객의 요구사항을 간단한 시나리오 표현한 것이다.
3. 릴리즈 계획 수립은 몇 개의 스토리가 적용되어 부분적으로 기능이 완료된 제품을 제공하는 것
4. 주기(이터레이션)은 하나의 릴리즈를 더 세분화 한 단위라고 부르며,
   약 1 ~ 3주간 진행하며, 새로운 스토리가 작성될 수도 있으며, 진행중 혹은 다음 주기에 포함하여 진행!
5. 승인 검사는 인수 테스트라고도 부르며, 주기 안에서 계획된 릴리즈 단위의 부분 완료 제품을 구현되면 수행하는 테스트이다.
   테스트가 완료되면 다음 주기를 진행합니다.
6. 소규모 릴리즈는 계획된 릴리즈 기간 동안 진행된 주기가 모두 완료되면 고객에 의한 최종 테스트를 수행한 후 릴리즈를 합니다.
   즉, 최종 결과물이 고객에서 전달되는 것이다.
```