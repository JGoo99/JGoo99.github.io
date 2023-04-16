---
layout: default
title: 오버로딩
parent: Java
grand_parent: Programing
nav_order: 19
---

# XVIII. 오버로딩

---

## 1. 정의

> 같은 네임이지만 서로 다른 매개변수의 형식을 갖고있는 매소드를 정의하는 것

---

## 2. 사용법

> 기존의 계산기 예제에서는 매개변수를 2개까지 받을 수 있었다
>
> 오버로딩을 이용하여 **2개 또는 3개의 매개변수**를 받을 수 있는 로직을 만들어보자

```java
class Cal {
  int left, right, third;
	
  public void setOprands(int left, int right) {
    this.left = left;
    this.right = right;
  }
	
  public void setOprands(int left, int right, int third) {
    this.left = left;
    this.right = right;
    this.third = third;
  }
	
  public void sum() {
    System.out.println( this.left + this.right + this.third );
  }
}

public class test {
	
  public static void main(String[] args) {
		
    Cal c1 = new Cal();
    c1.setOprands(10,20);
    c1.sum();
    c1.setOprands(10,20,30);
    c1.sum();
  }
}
```

> 같은 이름이지만 매개변수의 형식이 다른 매소드를 만들 수 있는 것은 오버로딩 덕분이다

{: .important-title }
> 🤔
>
> 중복이 발생하는 부분을 해결하고 싶다면?
>
> 오버로딩된 매소드를 아래처럼 수정하면 된다

```java
public void setOprands(int left, int right, int third) {
  this.setOprands(left, right);
  this.third = third;
}
```


---

## 3. 규칙

> 1. 같아야 하는 것: 메소드 이름, 리턴타입
>
> 2. 달라야 하는 것: 매개변수 형식
>
> +) 매개변수의 이름을 통해 매소드를 구분할 수 없음

{: .note-title }
> 🧐
>
> 규칙을 어겼을 경우를 알아보자

---

### i. 매개변수 동일, 리턴타입 상이

```java
class overloading {
	
  void A() {System.out.println( "void A()" );}
  void A(int args1) {System.out.println( "void A(int " + args1 + ")" );}
  void A(String args1) {System.out.println( "void A(String " + args1 + ")" );}
  int A() {System.out.println( "int A()" );}
}

public class test {
	
  public static void main(String[] args) {
		
    overloading a1 = new overloading();
    a1.A();
    a1.A(1);
    a1.A("hello");
  }
}
```

{: .warning-title }
> Error
>
> Duplicate method A() in type overloading
>
> a1.A()이 호출되었을 때, **void A()** 와 **int A()** 중 어느 것을 호출할 지 고를 수 없음

---

### ii. 리턴타입 동일, 매개변수 이름 상이

```java
void A(int args1) {System.out.println( "void A(int " + args1 + ")" );}
void A(int param1) {System.out.println( "void A(int " + param1 + ")" );}
```

> 매개변수의 이름은 매소드 안에서만 구분할 수 있고
>
> 호출 시(**a1.A(1);**)에 매개변수 이름을 언급하지 않으므로 자바 내에서 구분할 수 없다

---

## 4. 오버라이딩과의 차이점

> 하위클래스를 만들어 오버라이딩과의 차이점을 알아보자

_상위클래스_

```java
class super {
	
  void A() {System.out.println( "void A()" );}
  void A(int args1) {System.out.println( "void A(int " + args1 + ")" );}
  void A(String args1) {System.out.println( "void A(String " + args1 + ")" );}
}
```

_하위클래스_

```java
class sub extends super {
  void A(String args1, String args2) {System.out.println( "void A(String " + args1 + " " + args2 + ")" );}
  void A() {System.out.println("sub: void A()");}
}

public class test_sub {
	
  public static void main(String[] args) {
		
    overloading2 a1 = new overloading2();
    a1.A();
    a1.A(1);
    a1.A("hello");
    a1.A("hello", "hi");
  }
}
```

1. 오버라이딩이 된 매소드

```java
void A() {System.out.println("sub: void A()");}
```

> 매소드의 시그니처가 동일하면서, 하위클래스에 재정의된 경우이다

{:style="counter-reset:none"}
2. 오버로딩이 된 매소드

```java
void A(String args1, String args2) {System.out.println( "void A(String " + args1 + " " + args2 + ")" );}
```

> 매소드의 이름과 리턴 타입이 같으면서 매개변수가 다른 매소드로 오버로딩이 된 경우이다

---

## **이 개념을 왜 배울까?**

{: .highlight }
> 같은 기능의 메소드를 같은 이름으로 정의할 수 있다

> 사용자 입장에서 더 쉬운 설명서를 받는 것과 같다
> 
> 같은 기능임에도 매개변수의 개수에 따라 다른 이름의 매소드를 사용한다면
>
> 사용자 입장에서도 번거로울 것이다

---

[Link button](https://opentutorials.org/course/1223/6088){: .btn .btn-outline }
