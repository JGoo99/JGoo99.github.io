---
layout: default
title: 데이터 타입
parent: Java
nav_order: 1
---


# I. 데이터 타입

---

## 1. 숫자
_숫자는 따옴표 없이 입력_

```java
System.out.println(1+2);
```
### **변수 설정 방법**

- 정수

```java
int a = 1;

byte b = 2; //int형 숫자 사용 가능
short c = 3; //int형 숫자 사용 가능
long d = 4L; //int형 숫자에 L 붙여야 함
```

- 실수
```java
double a = 1.1;

float b = 2.2F; //임의적으로 float형 데이터롤 바꿈
```
---

## 2. 문자와 문자열

### 문자 : 한 글자
```java
System.out.prinln('깃'); //작은 따옴표
```

### 문자열 : 두 글자 이상

```java
System.out.prinln("깃허브"); //큰 따옴표
```

_문자열 안에 문자열을 사용하고 싶은 경우_

```java
System.out.prinln("Jin said \"hi\"");
```

_문자열 안에 줄바꿈을 사용하고 싶은 경우_
```java
System.out.prinln("Jin said \n\ hi");
```
###  **변수 설정 방법**

```java
String a = "coding";
```

[Link button](https://opentutorials.org/course/1223/5261){: .btn .btn-outline }