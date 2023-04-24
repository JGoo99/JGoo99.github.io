---
layout: default
title: 상속
parent: Java
grand_parent: Language
nav_order: 16
---

# XV. 상속

---

## 1. 정의

### i. 상속

> 기존의 객체에 있던 멤버를 새로운 객체에 넘겨주는 것

<br/>

### ii. 상하위 클래스

- 상위 클래스 : 부모 클래스(super / base)
- 하위 클래스 : 자식 클래스(sub   / derived)

---

## 2. 사용법

### i. 클래스와 매소드 만들기

```java
class subCal extends Cal {
  public void substract{
  }
}
```

> **extends Cal** 를 사용하여 상속받을 수 있다

<br/>

### ii. 메인에서 호출하기

```java
subCal c1 = new subCal();
```

> 호출할 때는 자식 클래스를 호출한다

<br/>

### iii. 실제 코드에서의 모습

```java
//Cal 클래스는 다른 자바파일에 저장되어있음
class subCal extends Cal {
  public void substract() {
    System.out.println( this.left - this.right );
  }
}

public class test {
	
  public static void main(String[] args) {
		
    subCal c1 = new subCal();
    c1.setOprands(10, 20);
    c1.sum();
    c1.substract();
  }
}
```

---

## 3. 상속의 중첩

> 더하기만 가능한 클래스를 곱셈만 가능한 클래스에 상속받고,
>
> 곱셈이 가능한 클래스를 나눗셈만 가능한 클래스에 상속받자 
>
> _Cal <- multiCal <- diviCal 로 상속을 중첩해보자_

```java
class diviCal extends multiCal {
  public void division() {
    System.out.println( this.left / this.right );
  }
}

public class test {
	
  public static void main(String[] args) {
		
    diviCal c1 = new diviCal();
    c1.setOprands(10, 20);
    c1.sum();
    c1.multiplication();
    c1.division();
  }
}
```

> 하나의 클래스를 호출하여 3가지 기능을 모두 사용할 수 있게되었다

---

## 4. 상속의 장단점

- 상속의 장점

> 코드중복을 없앨 수 있다 (부모 클래스는 적지 않아도 됨)
>
> 가독성의 증가 
>
> 유지보수의 편이성

<br/>

- 상속의 단점

> 상속 기능을 사용하기 위해 수많은 규칙과 변칙을 고려해야한다
>
> ~~이후 수업에서 다룰 예정이다~~

---

## **이 개념을 왜 배울까?**

{: .highlight }
> 클래스 원소스가 없을 때 유용하다

> 내가 만들지않은 클래스에 심지어 원소스가 없는 경우가 있다
>
> 이런 경우 특정 매소드를 클래스 소스에 추가하는 것이 불가능

<br/>

{: .highlight }
> 클래스 원소스 업데이트가 있을 가능성이 있다

> 클래스 원소스가 있더라도 업데이트를 통해 코드를 덮어쓰면
>
> 기존에 내가 추가했던 특정 매소드는 사라진다
>
> 그 매소드를 기억해뒀다가 추가하는 것도, 그것을 기억하고 있는 것도 비효율적이다

<br/>

{: .highlight }
> 더 쉬운 설명서(클래스)를 만들 수 있다

> 해당 클래스가 다양한 곳에 쓰이고 있는 경우, 내가 특정한 곳에만 필요한 매소드를 추가하게 되면
>
> 사용자 입장에서 그 매소드에 대해 공부를 해야 사용여부를 결정할 수 있는 번거로움이 있다

---

[Link button](https://opentutorials.org/course/1223/6060){: .btn .btn-outline }
