---
layout: default
title: 주석과 새미콜론
parent: Java
grand_parent: Language
nav_order: 3
---

# II. 주석과 새미콜론

---

## 1. 주석

### i. 한 줄 주석

```java
String a = "coding";
// 한 줄 주석 달기
```

<br/>

### ii. 여러줄 주석

```java
String b = "coding";
/*
두 줄 이상의
여러줄 주석 달기
*/
```

---

## 2. 세미콜론

_한 문장을 나타낼 때 사용_

```java
public void println(int x) {
  synchronized (this) {
    print(x);
    newLine();
  }
}
```

```java
int a = 100; double b = 10.1; //한 줄에 두 문장 가능
```

---

## **In my Opinion**

{: .highlight }
> 주석을 적게 써야 좋은 코드다

> 좋은 코드는 코드를 읽는 것 자체로 이해가 잘 되어야 한다
>
> 이해가 잘 되기 위해선 변수, 매소드, 함수 등의 이름을 잘 지어야 하며
>
> enter, space bar를 적재적소에 사용하여 가독성을 높여야 한다
>
> 그럼에도 불구하고 주석처리가 꼭 필요한 경우에 사용한다

---

## **이 개념을 왜 배울까?**

{: .highlight }
> 코딩은 혼자하는 것이 아니다

> 실무에 들어가면 팀 프로젝트, 협업이 대부분이다
>
> 나만 알아볼 수 있는 코드는 팀원에게 불편함으로 다가온다
>
> 기본적인 공통 원칙을 지키고, 필요한 부분에 주석처리를 함으로써 가독성을 높일 수 있어야 한다

---

[Link button](https://opentutorials.org/course/1223/6714){: .btn .btn-outline }