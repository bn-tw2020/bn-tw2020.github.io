---
layout: post
title: "PromiseAll"
categories: nodeJS
author: bn-tw2020
---
* content
{:toc}

## Intro

```
동기는 요청을 하는 시기와 응답을 받는 시기가 일치하며, 간단히 말해 요청을 하면 응답을 받는다.
비동기는 요청한 내용을 언젠간 응답해 줄 거이라는 약속을 의미한다.
```




---

## 동기

* 요청과 응답이 같은 시간대 안에 고정되어 있어, 요청에 대해 응답이 완료되기까지 프로그램이 정지한다. 
  응답을 받고나서야 비로소 다시 진행되는 특성을 가진다.

* 응답을 바로 받을 수 있고 그렇지 않을 수도 있다.

* 요청을 받는 곳이 처리속도가 어떠냐는 아무도 모르기 때문이다.

* 이러한 이유로 응답까지 대기시간을 필요로 한다.

* 어플리케이션이 잠시 멈춘다는 의미이다
    * ex) 클릭한 버튼이 응답을 받기까지 작동이 안되며, 버튼을 클릭 했는데,
          어떤 이유에서인지 응답이 없이 화면이 정지된 그런 상황이다.

## 비동기

* 요청 - 응답 간 결합이 자유로워 프로그램이 응답 받기 위해 대기하지 않고 쿨하게 자기 갈 길을 가는 특성이 존재한다.
  언젠간 응답을 받을테고 다음 로직을 수행한다.

* 응답을 바로 받을 수 있고 그렇지 않을 수도 있다.

* 요청을 받는 곳이 처리속도가 어떠냐는 아무도 모르기 때문이다.

* 이러한 이유로 응답까지 대기시간을 필요로 한다.

* 어플리케이션이 잠시 멈춘다는 의미이다
    * ex) 클릭한 버튼이 응답을 받기까지 작동이 안되며, 버튼을 클릭 했는데,
          어떤 이유에서인지 응답이 없이 화면이 정지된 그런 상황이다.

## 콜백함수(callBack)

```
"콜백함수는 자바스크립트의 비동기성을 표현하고 관리하는 가장 일반적인 기법이자 가장 기본적인 비동기 패턴이다(You don't know Js)"

그럼 콜백함수란 무엇일까?

"요청 처리가 완료되어 (다시) 사용하세요 !" 라는 신호이다.
  콜백함수에서 콜백이란 이름이 별로 있는 것이 아니라, 함수(function)가 있는데, 사용되는 목적/용도가 "call + back" 이라는 것입니다.

  콜백함수가 실행됐다는 것으로 요청한 작업이 끝났음을 알리고, 작업의 결과물을 콜백함수를 통해 사용가능하게 됩니다.

사용 된 예로, 클릭 이벤트가 발생할 때 출력되는 콜백 함수를 본적이 있을 것입니다.
```

### 콜백헬

* 콜백이 늘어나면 늘어날 수록 코드의 깊이가 늘어나 더 이상 헤어날 수 없다는 의미이다.

* 코드 관점에서 콜백함수는 중첩으로 들여쓰기가 반복되 가독성이 떨어진다.

* 그래서 Promise와 await 등의 방법이 존재한다.

## PromiseAll

* promise와 await 기본적인 이론은 추후 정리를 할 예정이다.

* 코드를 동기적으로 처리해야 할때 promise모듈을 사용할 수 있다.

### Promise.All

* 동기화 처리 할 Promise를 묶어서 한번에 실행

```javascript
const task1 = new Promise((resolve, reject) => resolve('즉시 호출'));

const task2 = new Promise((resolve, reject) => {
    setTimeout(() => resolve('3초 뒤 호출'), 3000);
});

Promise.all([task1, task2])
       .then(v => console.log(v));
```

### Promise.race

* promise들 중에서 제일 빠른 하나만을 실행

```javascript
const task3 = new Promise((resolve, reject) => {
    setTimeout(() => resolve(2000), 2000);
});

const task4 = new Promise((resolve, reject) => {
    setTimeout(() => resolve(), 0);
});

const result = Promise.race([task3, task4])
                      .then(v => console.log(v));

// 결과 값
// 0
```