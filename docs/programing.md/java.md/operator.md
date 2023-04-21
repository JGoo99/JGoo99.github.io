---
layout: default
title: 연산자
parent: Java
grand_parent: Programing
nav_order: 5
---

# IV. 연산자 

---

## 1. 산술 연산자

| 연산자   | 의미    |
|:-------|:-------|
| +      | 더하기   |
| -      | 빼기    |
| *      | 곱하기   |
| /      | 나누기   |
| -      | 나머지   |

<br/>

_연산자 중에 +는 문자열에도 사용 가능하다_
```java
String a = "안녕";
String b = "하세요";

System.out.println(a + b);
```

```
안녕하세요
```

---

## 2. 단항 연산자
_하나의 항을 대상을 이루어지는 연산자_

| 연산자   | 의미       |
|:-------|:----------|
| +      | 양수(사용x) |
| -      | 음수       |
| ++     | 1씩 증가   |
| --     | 1씩 감소   |

<br/>

```java
int i = 3;
i++			// i=i+1
System.out.println(i);    // 4
++i;
System.out.println(i);    // 5
System.out.println(++i);  // 6
System.out.println(i++);  // 6 i++는 print가 끝나고 더해지는 특징이 있음
System.out.println(i);    // 7
```

---

## 3. 비교 연산자

| 연산자    | 의미       |
|:--------|:----------|
| ==      | 같다       |
| !=      | 같지 않다   |
| >       | 크다       |
| >=      | 크거나 같다  |
| .equals | 같다(문자열) |

<br/>

_문자열 비교 예시_
```java
String a = "Hello world";
String b = new String("Hello world");

System.out.println(a == b);
System.out.println(a.equals(b));
```

```java
false
true
```

---

## 4. 논리 연산자

| 연산자    | 의미       |
|:--------|:----------|
| &&      | and       |
| /||     | or        |
| !       | not       |

<br/>

### i. && (and)

> ID와 PASSWORD가 모두 맞아야 하는 로그인 로직을 만들어보자

```java
String id = args[0];
String password = args[1];
		
if (id.equals("Goo") && password.equals("111")) {
  System.out.println("login");
} else {
  System.out.println("worng");
}
```

<br/>

### ii. || (or)

> ID가 둘 중 하나라도 맞으면 되는 로그인 로직을 만들어보자

```java
String id = args[0];
		
if (id.equals("Goo") || id.equals("goo")) {
  System.out.println("login");
} else {
    System.out.println("worng");
}
```

<br/>

### iii. ! (not)

> not 연산자를 if조건문에 사용해보자

```java
if (!true) {
  System.out.println(1);
}
if (!false) {
  System.out.println(2);
}
```

```java
2
```

---

## 5. 기본연산자의 우선순위

![operator](https://user-images.githubusercontent.com/126454114/233689592-014c1e43-0931-413a-bcff-d2a677e07c7e.jpg)

---

## **이 개념을 왜 배울까?**

{: .highlight }
> 연산자는 조건문의 기본이다

> 조건문에서의 연산자 작성 실수는 완전히 틀린 답을 도출할 수 있다
>
> 그 오답이 프로젝트 내에서 치명적인 오류로 이어질 수 있다
>
> 만약, 오류 원인을 밤새 찾았는데 그 원인이 연산자 실수라고 생각해보자
>
> 기본 중의 기본인 연산자는 정확히 알아두는 것이 필요하다

---

[Link button](https://opentutorials.org/course/1223/5331){: .btn .btn-outline }