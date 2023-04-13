---
layout: default
title: 상속과 생성자
parent: Java
grand_parent: Programing
nav_order: 17
---

# XVI. 상속과 생성자

---

## 1. 기본 생성자

> 객체를 생성할 때 java가 자동으로 만들어준 생성자

```java
public class test {
	
  public static void main(String[] args) {
    test c1 = new test();
	}
}
```

{: .highlight }
> 자기자신(class_test)을 매인에서 객체로 생성할 수 있다
>
> 여기서 중요한 것은 아래의 경우다

```java
public class test {
	
  //public test() {}
  public test(int prami1) {}
	
  public static void main(String[] args) {
    test c1 = new test();
  }
}
```

{: .warning-title }
> Error
>
> the constructor test() is undefined

> 매개변수가 있는 생성자가 있을 때는 기본생성자를 자동으로 만들어주지 않는다
>
> 따라서 주석처리 되어있는 기본생성자를 추가해주어야 한다

---

## 2. Super()

> 상위 클래스의 생성자를 의미한다
>
> 이 개념을 알기 위해서 먼저 이전에 다루었던 계산기 클래스를 보자

### i. 기존 계산기 클래스

```java
class Cal {
  int left, right;
	
  public void setOprands(int left, int right) {
    this.left = left;
    this.right = right;
  }
	
  public void sum() {
    System.out.println( this.left + this.right );
  }
}

class diviCal extends Cal {
	
  public void division() {
    System.out.println( this.left / this.right );
  }
}

public class test {
	
  public static void main(String[] args) {
		
    diviCal c1 = new diviCal();
    c1.setOprands(20, 10);
    c1.sum();
    c1.division();
  }
}
```

---

### ii. 기존 클래스에 생상자 기능 추가

> 상위 클래스에서 setOprands를 지우고 생성자기능을 사용해보자

```java
class Cal {
  int left, right;
	
  public Cal(int left, int right) {  //생성자로 변경
    this.left = left;
    this.right = right;
  }
//매소드 sum() 생략
class diviCal extends Cal {
	
  public diviCal(int left, int right) { //생성자 추가
		this.left = left;
		this.right = right;
	}

  public void division() {
    System.out.println( this.left / this.right );
  }
}

public class test {
	
  public static void main(String[] args) {
		
    diviCal c1 = new diviCal(20, 10);
    //setOprands 삭제
    c1.sum();
    c1.division();
  }
}
```

{: .warning-title }
> Error
>
> Implicit super constructor Cal() is undefined for default constructor. Must define an explicit constructor
>
> 매개변수가 있는 클래스가 있기 때문에 기본생성자가 자동 생성되지 않았고,
>
> 매인에서 하위 클래스를 호출하면 자동으로 상위 클래스의 기본생성자를 호출한다
>
> 따라서 존재하지않은 생성자를 호출한 것이므로 위와 같은 오류가 발생한다

---

### iii. 해결방법

- 상위 클래스에서 기본생성자를 추가해준다

```java
public Cal() {}
```

> 기본생성자가 없어서 생긴 오류이니, 그저 추가만 해주면 오류가 해결된다

{: .important-title }
> 🧐
>
> 하지만 생성자 **코드의 중복**이 발생한다
>
> 오류를 제거하면섣 코드의 중복을 막을 수 있는 방법이 **super()** 이다

```java
class Cal {
  int left, right;
	
  public Cal(int left, int right) {
    this.left = left;
    this.right = right;
  }
	
  public void sum() {
    System.out.println( this.left + this.right );
  }
}

class diviCal extends Cal {
	
  public diviCal(int left, int right) {
    super(left, right);
  }
	
  public void division() {
    System.out.println( this.left / this.right );
  }
}

public class test {
	
  public static void main(String[] args) {
		
    diviCal c1 = new diviCal(20, 10);
    c1.sum();
    c1.division();
  }
}
```

_생성자 코드가 1000줄 이상이었다면 분명히 효율적인 방법이다_

{: .important-title }
> ❗️
>
> 단, super()를 가장 먼저 사용해야한다

---

[Link button](https://opentutorials.org/course/1223/6126){: .btn .btn-outline }
