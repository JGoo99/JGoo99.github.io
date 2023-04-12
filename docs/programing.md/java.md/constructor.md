---
layout: default
title: 초기화와 생성자
parent: Java
grand_parent: Programing
nav_order: 15
---

# XIV. 초기화와 생성자

---

## 1. 초기화

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
    c1.setOprands(10, 20);
    c1.sum();
    c1.avg();
  }
}
```

> c1 객체를 사용하기 위해서는 아래의 초기화 단계가 필요하다

```java
c1.setOprands(10, 20);
```

> 이 단계가 없이 sum과 avg 매소드를 사용하게 되면 오류가 발생한다
>
> 위와 같이 반드시 초기화 단계가 필요한 경우,
>
> 객체지향에서 제공하는 **생산자** 기능이 있다

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

> 객체 생성 시에 최기화 작업을 강제할 수 있다

---

## +. 나의 궁금증

### 1. 멤버 생성 방법

> left와 right를 클래스에서 선언할 때
>
> static / non-static 결정이 헷갈렸다
>
> 멤버 수업에서 들은 내용을 떠올려보자 

{: .important }
> 언제 클래스 변수를 선언하는 것이 좋을까?
>
> ~~1. 인스턴스에 따라서 변하지 않는 값이 필요한 경우 (ex.π)~~
>
> ~~2. 값의 변경 사항을 모든 인스턴스가 공유해야 하는 경우~~
>
> ~~3. 인스턴스를 생성할 필요가 없는 값을 클래스에 저장하고 싶은 경우~~

_이번 클래스의 경우 인스턴스를 생성하며 계속해서 값이 초기화되기 때문에 굳이 전역변수로 선언할 필요가 없다_


#### ii. 지역변수로 설정

{: .highlight-title }
> non-static 변수로 선언
>
> 일단 두 변수 모두 class 내에서 전역으로 사용하기 때문에 전역 선언 가능
>
> 단 매소드 내 변수명과 같기 때문에 초기화할 때 오류 발생
>
> 따라서 매소드 매개변수 명을 변경하면 된다 _(아래 참고)_

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
