---
layout: default
title: 클래스와 인스턴스
parent: 객체지향프로그래밍
grand_parent: Java
nav_order: 2
---

# II. 클래스와 인스턴스

---

## 1. 정의

- 클래스 : 설계도 / 매소드의 정의
- 인스턴스 : 제품 / 매소드의 호출

---

## 2. Refactoring

_기존 코드의 문제를 개선하고 더욱 효율적이게 만드는 과정_

> 가독성, 재활용성, 유지보수의 향상을 기대할 수 있음 _(아래 예시)_

---

### i. 매소드화

```java
public static void main(String[] args) {
  System.out.println(10 + 20);
  System.out.println(20 + 26);
}
```

{: .highlight }
> 위의 코드를 **매소드화** 해보자!

```java
public static void sum(int left, int right) {
  System.out.println(left + right);
}

public static void main(String[] args) {
  sum(10, 20);
  sum(20, 60);
}
```

{: .highlight }
> 객체의 로직을 알기때문에 sum(a,b)의 해석이 쉽다 (가독성)
> sum 객체는 다른 코드에도 활용이 가능하다 (재활용성)
> 객체 수정이 전체 매인 sum(a,b)에 대한 수정으로 이루어진다 (유지보수)

---

### ii. 변수화

```java
int left, right;
left = 10; right = 20;

//이 사이에 수많은 로직이 추가될 수 있음

sum(left, right);
```

> 변수와 로직 사이에 간격이 넓어지면서 유지보수가 어려워짐
>
> 이러한 문제들을 해결하기 위한 언어개발자들의 고민들이 있었을 것

"이러한 맥락에서 **객체지향프로그래밍** 이 등장한 것이다"

---

### iii. 객체화


---

[Link button](https://opentutorials.org/course/1223/5400){: .btn .btn-outline }

[Link button](https://opentutorials.org/course/1223/5440){: .btn .btn-outline }