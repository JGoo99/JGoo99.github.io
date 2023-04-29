---
layout: default
title: 초기화와 생성자
parent: Java 기초
grand_parent: Language
nav_order: 15
---

# XIV. 초기화와 생성자

---

## 1. 초기화

> 초기화가 무엇인지 아래 코드를 통해 알아보자

```java
class Calculator {
  int left, right;
	
  public void setOprands (int left, int right) {
    this.left = left;
    this.right = right;
  }
	
  public void sum() {
    System.out.println( this.left + this.right );
  }
	
  public void avg() {
    System.out.println( (this.left + this.right) / 2 );
  }
}

public class test {
	
  public static void main(String[] args) {
    Calculator c1 = new Calculator();
    c1.setOprands(10, 20); //초기화
    c1.sum();
    c1.avg();
  }
}
```

> 위처럼 c1 객체를 사용하기 위해서는 아래의 초기화 단계가 필요하다

```java
c1.setOprands(10, 20);
```

> 이 단계가 없이 sum과 avg 매소드를 사용하게 되면 오류가 발생한다
>
> 위와 같이 반드시 초기화 단계가 필요한 경우
>
> 객체지향에서 제공하는 **생성자** 기능이 있다

---

## 2. 생성자

> 객체지향 프로그래밍의 초기화에 해당하는 기능

```java
class Calculator {
  int left, right;
	
  public Calculator (int left, int right) {
    this.left = left;
    this.right = right;
  }
// 아래 생략
```

> 위의 경우 아래처럼 호출하면 된다

```java
Calculator c1 = new Calculator(10,20);
```

> 객체 생성 시에 초기화 작업을 강제할 수 있다 (오류 가능성x)

---

## +. 나의 궁금증

### 궁금증1) "변수를 어떤 소속으로 생성해야 하지??"

> left와 right를 클래스에서 선언할 때 static / non-static 결정이 헷갈렸다
>
> 멤버 수업에서 들은 내용을 떠올려보자 

{: .important-title }
> 언제 클래스 변수를 선언하는 것이 좋을까?
>
> ~~1. 인스턴스에 따라서 변하지 않는 값이 필요한 경우 (ex.π)~~
>
> ~~2. 값의 변경 사항을 모든 인스턴스가 공유해야 하는 경우~~
>
> ~~3. 인스턴스를 생성할 필요가 없는 값을 클래스에 저장하고 싶은 경우~~

_이번 클래스의 경우 인스턴스를 생성하며 계속해서 값이 초기화되기 때문에 **굳이 전역변수로 선언할 필요가 없다**_


<br/>

> 그렇다면 non-static 변수로 선언해보자

```java
class Calculator {
  int left, right;
	
  public Calculator (int left, int right) {
    left = left; //중복 오류
    right = right; //중복 오류
  }
```

{: .warning-title }
> Error
>
> 매소드 밖과 안의 변수명 중복 오류 발생

<br/>

- 해결방법

> 변수를 구분만 해주면 된다
> 
> 1. **this.변수** 활용하기
>
> 2. 매소드내 변수명을 **_left, _right**로 변경하기 

<br/>

1. **this.변수** 활용하기

```java
class Calculator {
  int left, right;
	
  public Calculator (int left, int right) {
    this.left = left;
    this.right = right;
  }
```

<br/>

{:style="counter-reset:none"}
2. 매소드내 변수명을 **_left, _right**로 변경하기 

```java
class Calculator {
  int left, right;
	
  public Calculator (int _left, int _right) {
    left = _left; 
    right = _right; 
  }
```

<br/>

### 궁금증2) "그럼 클래스 변수로 선언하면 어떻게 될까??"

> left, right를 클래스 변수로 선언해보자

```java
class Calculator {
  static int left, right;
	
  public Calculator (int left, int right) {
    this.left = left; 
    this.right = right; 
  }
```

> 일단 클래스 변수에 this(인스턴스)로 접근할 필요가 없다
>
> 따라서 결과는 정상출력되지만, 아래와 같은 메시지가 뜬다

{: .highlight-title }
> ❗️
>
> the static field should be accessed in a static way

<br/>

- 해결방법

> 접근 방법을 static 방법으로 바꿔준다
>
> 1. **Calculator.left** 사용하기
>
> 2. this를 지우고 매소드 변수명 변경하기 (this를 지워도 전역변수에 접근O)

<br/>

1. **Calculator.left** 사용하기

```java
class Calculator {
  static int left, right;
	
  public Calculator (int left, int right) {
    Calculator.left = left; 
    Calculator.right = right; 
  }
```

<br/>

{:style="counter-reset:none"}
2. this를 지우고 매소드 변수명 변경하기

```java
class Calculator {
  static int left, right;
	
  public Calculator (int _left, int _right) {
    left = _left; 
    right = _right; 
  }
```

---

## **이 개념을 왜 배울까?**

{: .highlight }
> 더 쉬운 사용법으로 만드는 것이다

> 사용자가 숙지하고 있지 않으면 오류가나는 코드를 정교화하여
>
> 옳은 방법으로 잘 인도하여 오류 가능성을 낮출 수 있는 방법이었다
>
> 특히 객체의 초기화 과정은 자주 나올텐데, 외워두면 좋을 듯 하다 

---

[Link button](https://opentutorials.org/course/1223/5519){: .btn .btn-outline }
