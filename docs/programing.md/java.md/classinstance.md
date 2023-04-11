---
layout: default
title: 클래스와 인스턴스
parent: Java
grand_parent: Programing
nav_order: 12
---

# II. 클래스와 인스턴스

> 클래스와 인스턴스의 관계를 이해하는 것이 중요하다

---

## 1. 정의

- 클래스

> 일종의 설계도라고 할 수 있다
>
> 즉, 매소드를 정의하는 것이며
>
> 사용자 정의 데이터 타입을 만드는 것이다
>
> 프로그램 안의 프로그램이라고 생각하면 된다

- 인스턴스

> 클래스가 설계도라면 인스턴스는 제품이다
>
> 하나의 구체적인 객체이며
> 
> 정의된 클래스를 호출하는 것이다

---

## 2. Refactoring

_기존 코드의 문제를 개선하고 더욱 효율적이게 만드는 과정_

> 가독성, 재활용성, 유지보수의 향상을 기대할 수 있음 _(아래 예시)_


### i. 매소드화

```java
public static void main(String[] args) {
  System.out.println(10 + 20);
  System.out.println(20 + 60);
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

{: .highlight-title }
> Refactoring의 장점
>
> 객체의 로직을 알기때문에 sum(a,b)의 해석이 쉽다 (가독성)
>
> sum 객체는 다른 코드에도 활용이 가능하다 (재활용성)
>
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

> 클래스와 인스턴스를 활용하여 객체화 해보자
>
> 계산(덧셈, 평균) 로직의 클래스를 만들고, 메인에서 인스턴스로 호출하기

```java
class Calculator {
	
  int left, right;
  //인스턴스 변수
	
  public void setOprands(int left, int right) {
    this.left = left;
    this.right = right;
  }
	
  public void sum() {
    System.out.println(this.left + this.right);
  }
	
  public void avg() {
    System.out.println( (this.left + this.right) / 2);
  }
}

public class calculatorDemo1 {
	
  public static void main(String[] args) {
		
    Calculator c1 = new Calculator(); 
    //Calculator가 클래스로 만든 데이터 타입임
    c1.setOprands(10,20);
    c1.sum();
    c1.avg();
		
    Calculator c2 = new Calculator();
    c2.setOprands(30, 60);
    c2.sum();
    c2.avg();
  }
}
```

---

# **이 개념을 왜 배울까?(my opinion)**

- 객체화의 재료이다

> 클래스를 만들고 인스턴스를 만드는 과정이 객체화이다
>
> 클래스/인스턴스가 무엇인지, 어떻게 생성하고 호출하는지 알아야 객체지향이 가능하다

---

[Link button](https://opentutorials.org/course/1223/5400){: .btn .btn-outline }