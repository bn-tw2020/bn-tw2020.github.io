---
layout: post
title: "개인키와 공개키"
categories: etc
author: bn-tw2020
---
* content
{:toc}

## Intro

```
암호 알고리즘은 패스워드, 주민번호, 은행계좌와 같은 중요정보를 보호하기 위해
평문을 암호화된 문장으로 만드는 절차이다.
```




---

## 암호 알고리즘

1. 암호 알고리즘은 해시(Hash)를 사용하는 단방향 암호화 방식

2. 개인키 및 공개키로 분류되는 양방향 암호화 방식이 존재

<img width="666" alt="스크린샷 2021-02-25 오후 3 19 08" src="https://user-images.githubusercontent.com/66770613/109111841-fda48600-777c-11eb-977a-4948ce1999cd.png">

## 개인키 암호화

* 개인키 암호화 기법은 동일한 키로 데이터를 암호화하고 복호화한다.

* 대칭 암호 기법, 단일키 암호화 기법이라고 부른다.

* 한 번에 하나의 데이터 블록을 암호화 하는 블록 암호화 방식
  평문과 동일한 길이의 스트림을 생성하여 비트 단위로 암호화 하는 스트림 암호화 방식이 존재한다.

<img width="726" alt="스크린샷 2021-02-25 오후 3 19 25" src="https://user-images.githubusercontent.com/66770613/109111856-009f7680-777d-11eb-96fe-8a2e72941873.png">  

```
1. 데이터베이스 사용자는 평문의 정보 M을 암호화 알고리즘 E와 개인키 K를 이용하여 암호문 C로 바꾸어 저장시킨다.
2. 사용자는 데이터베이스에 접근하기 위해 복호화 알고리즘 D와 개인키 K를 이용하여 다시 평문의 정보 M으로 바꾼다.

종류
1. 블록 암호화 방식 : DES, SEED, AES, ARIA
2. 스트림 암호화 방식 : LFSR, RC4

장점
1. 암호화/복호화 속도가 빠르다.
2. 알고리즘이 단순하며, 공개키 암호 기법보다 파일 크기가 작다.

단점
1. 사용자의 증가에 따라 관리해야 할 키의 수가 상대적으로 많다.
```

## 공개키 암호화

* 데이터를 암호화할 때 사용하는 공개키는 데이터 베이스 사용자에게 공개
  복호화할 때의 비밀키는 관리자가 비밀리에 관리한다.

* 비대칭 암호 기법이라 부른다.

*  대표적으로 RSA기법이 존재한다.

<img width="726" alt="스크린샷 2021-02-25 오후 3 19 40" src="https://user-images.githubusercontent.com/66770613/109111862-0432fd80-777d-11eb-85a9-6450770195c6.png">

```
1. 데이터베이스 사용자는 평문의 정보 M을 암호화 알고리즘 E와 공개키 P를 이용하여 암호문 C로 바꾸어 저장한다.
2. 복호화하기 위해서는 비밀키와 복호화 알고리즘에 권한이 있는 사용자만이 사용할 수 있다.
3. 복호화 알고리즘 D와 비밀키 S를 이용하여 다시 평문의 정보 M으로 바꾼다.

장점
1. 키의 분배가 용이하다.
2. 관리해야 할 키 개수가 적다.

단점
1. 암호화/복호화 속도가 느리다.
2. 알고리즘이 복잡하다.
3. 개인키 암호화 기법보다 파일의 크기가 크다.
```

## 공개키 기반 구조

* PKI(Public Key Infrastructure)이라고 부른다.

* 공개키 암호 시스템을 안전하게 사용하고 관리하기 위한 정보 보호 표준 방식
  ITU-T의 X.509 방식과 비X.509 방식으로 구분된다.

* X.509 : 인증기관에서 발생하는 인증서를 기반으로 상호 인증을 제공

* 비X.509 : 국가별, 지역별로 맞게 보완 및 개발

## 양방향 알고리즘 종류

```
1. SEED
   한국 KISA에서 개발한 블록 암호화 알고리즘
   블록 크기는 128bit, 키 길이에 따라 128, 256bit로 분류한다.

2. ARIA
   국가정보원, 산학연협회가 개발한 블록 암호화 알고리즘
   블록 크기는 128bit, 키 길이에 따라 128, 256bit로 분류한다.

3. DES
   미국에서 발표한 개인키 암호화 알고리즘
   DES를 3번 적용하여 보안을 더욱 강화한 3DES도 있다.
   블록 크기는 64bit, 키 길이는 56bit

4. AES
   미국에서 발표한 개인키 암호화 알고리즘
   DES의 한계를 느낀 후 공모한 후 발표했다.
   블록 크기는 128bit, 키 길이에 따라 128, 192, 256bit로 분류한다.

5. RSA
   MIT에서 제안된 공개키 암호화 알고리즘
   큰 숫자를 소인수분해 하기 어렵다는 것에 기반하여 만들어졌다.
   공개키와 비밀키를 사용하는데, 여기서 키란 메시지를 열고 잠그는 상수를 의미한다.
```

## 다음글

<a href = "https://bn-tw2020.github.io/2021/02/25/3hash-encryption/">단방향 암호화 Hash</a>