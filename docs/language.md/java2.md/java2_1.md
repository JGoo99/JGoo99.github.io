---
layout: default
title: 변수
parent: Java 심화
grand_parent: Language
nav_order: 2
---

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

# I. 변수
{: .no_toc }

---

## 변수와 상수

### i. 변수란?
{: .no_toc }

> **단 하나의 값을 저장할 수 있는 메모리 공간**
>
> 이 수는 변경할 수 있기 때문에 변수라고 명명

<br/>

### ii. 변수의 선언과 초기화
{: .no_toc }

- **변수의 선언**

> 변수를 사용하기 위해 변수 타입과 이름을 정하는 것

```java
int age;
//변수타입 변수이름
```

- **변수의 초기화**

> **변수를 사용하기 전에 처음으로 값을 저장하는 것**
>
> 오른쪽의 값을 왼쪽에 대입한다

```java
int age = 24, year = 2023;
```

<br/>

{: .new-title }
> 두 변수의 값 교환하기
>
> x와 y에 각각 초기화된 값을 바꿔보자

```java
class Main {
  public static void main(String[] args) {
    int x=5, y=10;
    int temp = 0;

    System.out.println("x:" + x + " y:" + y);

    temp = x; 
    x = y;
    y = temp;

    System.out.println("x:" + x + " y:" + y);
  }
}
```

```java
x:5 y:10
x:10 y:5
```

> 단순히 x=y, y=x로 초기화 하는 것이 아니라
>
> 임시저장소 temp를 선언하여 두 변수 x,y의 값을 교환해야 한다

<br/>

### iii. 변수의 명명규칙
{: .no_toc }

- 대소문자가 구분되며 길이에 제한이 없다

- 예약어를 사용해서는 안 된다

- 숫자로 시작해서는 안 된다

- 특수문자는 _와 $만 허용된다

- 클래스 이름의 첫글자는 항상 대문자로 한다

- 여러 단어로 이루어진 이름은 단어의 첫 글자를 대문자로 한다

- 상수의 이름은 모두 대문자로 한다 (여러 단어로 이루어진 경우 _로 구분한다)


---

## 변수의 타입

### i. 기본형과 참조형
{: .no_toc }

- **자료형**

> data의 type에 따라 값이 저장될 공간의 크기와 저장형식을 정의한 것으로
>
> 자료형은 크게 기본형과 참조형으로 나뉜다

- **참조형**

> 어떤 값이 저장된 주소를 값으로 저장하는 자료형이다 

```java
Data today = new Data();
//클래스이름 변수이름 = 생성된 객체의 주소
```

- **기본형**

> 실제 값을 저장하는 자료형으로 문자형, 정수형, 실수형, 논리형 등이 있다

|분류     |타입                       |
|:-------|:-------------------------|
|논리형    |boolean                   |
|문자형    |char                      |
|정수형    |byte, short, **int**, long|
|실수형    |float, **double**         |

> 기본형의 종류와 크기는 아래와 같다

|종류/크기  |  1byte  |  2byte  |  4byte  |  8byte  |
|----:----|----:----|----:----|----:----|----:----|
|논리형     |boolean  |         |         |         |
|문자형     |         |char     |         |         |
|정수형     |byte     |short    |**int**  |long     |
|실수형     |         |         |float    |**double**|

<br/>

### ii. 상수와 리터럴
{: .no_toc }

- 상수

> 값을 저장할 수 있는 공간 (단, 값을 변경할 수 없으며, **선언과 동시에 초기화해야 한다**)

```java
final int MAX_VALUE = 100; 
```

- 리터럴

> 숫자 그 자체의 값으로, 선언 시 접미사가 필요한 경우가 있다



### iii. 형식화된 출력
{: .no_toc }

### vi. 화면에서 입력받기
{: .no_toc }

---

## 진법

### i. 10진법과 2진법
{: .no_toc }

### ii. 비트와 바이트
{: .no_toc }

### iii. 8진법과 16진법
{: .no_toc }

### vi. 정수의 진법변환
{: .no_toc }

### v. 실수의 진법변환
{: .no_toc }

### vi. 2의 보수법
{: .no_toc }

---

## 기본형

### i. 논리형
{: .no_toc }

### ii. 문자형
{: .no_toc }

### iii. 정수형
{: .no_toc }

### vi. 실수형
{: .no_toc }

---

## 형변환

### i. 형변환이란?
{: .no_toc }

### ii. 형변환 방법
{: .no_toc }

### iii. 정수형 간의 형변환
{: .no_toc }

### vi. 실수형 간의 형변환
{: .no_toc }

### v. 정수형과 실수형 간의 형변환
{: .no_toc }

### vi. 자동 형변환
{: .no_toc }