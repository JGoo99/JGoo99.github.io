---
layout: default
title: 객체지향프로그래밍I
parent: Java 심화
grand_parent: Language
nav_order: 6
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

# V.객체지향언어
{: .no_toc }

---

## 객체지향언어

### i. 역사
{: .no_toc }

- **객체지향이론의 기본개념**

> "실제 세계는 사물(객체)로 이루어져 있으며, 발생하는 모든 사건들은 사물간의 상호작용이다."

> 원래는 비주류 언어였지만 인터넷의 발전과 시대의 흐름에 맞추어 현재는 주류 언어로 자리잡았다.

<br/>

### ii. 특징
{: .no_toc }

1. **코드의 재사용성이 높다**

> 새로운 코드를 작성할 때 기존의 코드를 이용하여 쉽게 작성할 수 있다.

<br/>

{:style="counter-reset:none"}
2. **코드의 관리가 용이하다**

> 코드간의 관계를 이용해서 적은 노력으로 쉽게 코드를 변경할 수 있다.

<br/>

{:style="counter-reset:none"}
3. **신뢰성이 높은 프로그래밍을 가능하게 한다**

> 제어자와 메서드를 이용해서 데이터를 보호하고, 올바른 값을 유지하도록 하며,
>
> 코드의 중복을 제거하여 코드의 불일치로 인한 오동작을 방지할 수 있다.

<br/><br/>

---

## 클래스와 객체

### i. 정의와 용도
{: .no_toc }

1. **클래스**

> 정의: 객체를 정의해 놓은 것이다.
>
> 용도: 객체를 생성하는데 사용한다. 객체의 설계도 또는 틀 

<br/>

2. **객체**

> 정의: 실제로 존재하는 것. 사물 또는 개념.
>
> 용도: 객체가 가지고 있는 기능과 속성에 따라 다름.

{: .note }
> 유형의 객체: 책상, 의자, 자동차와 같은 사물
>
> 무형의 객체: 수학공식, 프로그램 에러와 같은 논리와 개념
>
> **객체지향이론에서는 객체의 정의에 유형과 무형의 객체를 모두 포함한다.**

<br/>

### ii. 객체와 인스턴스
{: .no_toc }

- **인스턴스**

> 어떤 클래스로부터 만들어진 객체를 그 클래스의 **인스턴스**라고 한다.
>
> 클래스로부터 객체를 만드는 과정을 클래스의 **인스턴스화**라고 한다.

{: .highlight }
> **책상은 객체이며, 책상 클래스의 인스턴스다.**
>
> 인스턴스는 어떤 클래스로부터 만들어진 것인지를 강조한다.

<br/><br/>

### iii. 객체의 구성요소 - 속성과 기능
{: .no_toc }

1. **정의**

> 객체는 속성(멤버)과 기능(매서드)의 집합체이다.

<br/>

{:style="counter-reset:none"}
2. **용어 정리**

> **속성**: 맴버변수(member variable), 특성(attribute), 필드(field), 상태(state)
>
> **기능**: 매서드(method), 함수(function), 행위(behavior)

<br/>

_ex) TV_

> 멤버: 색깔, 전원상태, 채널 등
>
> 기능: 끄기와 켜기, 채널 변경하기 등

```java
class TV {
  String color;  //색깔
  boolean power; //전원상태
  int channel;   //채널

  void power() {power = !power;}
  void channelUp() {channel++;}
  void channelDown() {channel--;}
}
```

<br/><br/>

### iv. 인스턴스의 생성과 사용
{: .no_toc }

1. **인스턴스 생성**

> **클래스명 변수명;**
>
> 클래스의 객체를 참조하기 위한 참조변수를 선언
>
> **변수명 = new 클래스명();**
>
> 클래스의 객체를 생성 후, 객체의 주소를 참조변수에 저장

```java
TV t;         //TV클래스 타입의 참조변수 t를 선언
t = new TV(); //TV인스턴스를 생성한 후, 생성된 TV인스턴스의 주소를 t에 저장
```

<br/>

{:style="counter-reset:none"}
2. **인스턴스 사용**

```java
class Tv {
  //TV의 속성(멤버변수)
  String color;
  boolean power;
  int channel;

  //TV의 기능(매서드)
  void power() {power = !power;}
  void channelUp() {channel++;}
  void channelDown() {channel--;}
}

class TvTest {
  public static void main(String[] args) {
    Tv t;
    t = new Tv();
    t.channel = 7;    //참조변수.멤버변수
    t.channelDown();
    System.out.printf("Tv Channel: %d", t.channel);
  }
}
```

```java
Tv Channel: 6
```

> 참조변수 t를 이용하여 매서드 channelDown을 호출하여 사용한다.
>
> **t.channel=7;**: 참조변수를 통해 멤버변수를 초기화한다.
>
> **t.channelDown();**: 참조변수를 통해 매서드를 호출하여 멤버변수의 값을 감소시킨다.

{: .important }
> 인스턴스는 참조변수를 통해서만 다룰 수 있으며, 참조변수의 타입은 인스턴스의 타입과 일치해야한다.

<br/>

{:style="counter-reset:none"}
3. **인스턴스간의 관계**

1. 

<br/><br/>

### v. 객체 배열
{: .no_toc }

<br/><br/>

### vi. 클래스의 또 다른 정의
{: .no_toc }

<br/><br/>

---

## 변수와 매서드

### i. 선언 위치에 따른 변수의 종류
{: .no_toc }

<br/><br/>

### ii. 클래스변수와 인스턴스변수
{: .no_toc }

<br/><br/>

### iii. 매서드
{: .no_toc }

1. **사용하는 이유**

<br/>

2. **선언과 구현**

<br/>

3. **호출**

<br/><br/>

### iv. return 문
{: .no_toc }

<br/><br/>

### v. JVM의 메모리 구조
{: .no_toc }

<br/><br/>

### vi. 매개변수
{: .no_toc }

1. **기본형 매개변수**

<br/>

2. **참조형 매개변수**

<br/><br/>

### vii. 참조형 변환타입
{: .no_toc }

<br/><br/>

### viii. 재귀호출
{: .no_toc }

<br/><br/>

### ix. 클래스매서드와 인스턴스 매서드
{: .no_toc }

<br/><br/>

### x. 클래스멤버와 인스턴스멤버의 창조와 호출
{: .no_toc }

<br/><br/>

---

## 오버로딩

### i. 정의와 조건
{: .no_toc }

<br/><br/>

### ii. 예시
{: .no_toc }

<br/><br/>

### iii. 장점
{: .no_toc }

<br/><br/>

### iv. 가변인자와 오버로딩
{: .no_toc }

<br/><br/>

---

## 생성자

### i. 정의
{: .no_toc }

<br/><br/>

### ii. 기본생성자
{: .no_toc }

<br/><br/>

### iii. 매개변수가 있는 생성자
{: .no_toc }

<br/><br/>

### iv. 생성자에 따른 생성자 호출
{: .no_toc }

<br/><br/>

### iv. 생성자를 인용한 인스턴스의 복사
{: .no_toc }

<br/><br/>

---

## 변수의 초기화

### i. 정의
{: .no_toc }

<br/><br/>

### ii. 명시적 초기화
{: .no_toc }

<br/><br/>

### iii. 초기화 목적
{: .no_toc }

<br/><br/>

### iv. 매개변수 초기화 시기와 순서
{: .no_toc }


