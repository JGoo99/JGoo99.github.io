---
layout: default
title: 형 변환
parent: Java
grand_parent: Programing
nav_order: 4
---

# III. 형 변환
_데이터 타입을 변경하는 것_

---

## 1. 암시적 형 변환
_표현 범위가 좁은 데이터 타입에서 넓은 데이터 타입으로 자동 변환_
```
byte - short, char - int - long - float - double
```

**EX**

```java
int a = 3;			
float b = 1.0F;		//(int->float)   (float -> double)
double c = a + b;	//3.0F + 1.0F = 4.0F -> 4.0
```

---

## 2. 명시적 형 변환
_위의 규칙에 위반되어 자동으로 변환되지 않는 경우, 수동으로 변환 처리를 해야한다_
```java
float a = (float)100.0;
int b = (int)100.0F;
```

**EX**

```java
int a = 10;
float b = 3.0F;

System.out.println(a/b);
```
---

# **이 개념을 왜 배울까?(my opinion)**

- 형변환

> java는 변수의 데이터 타입을 엄격하게 통제한다
>
> 또한 어떤 결과 값을 가져오고 보내는 형변환 과정이 종종 발생하기 때문에
>
> 객체지향 수업 전에 형변환에 대한 기본 개념을 탄탄히 해야한다

---

[Link button](https://opentutorials.org/course/1223/5330){: .btn .btn-outline }