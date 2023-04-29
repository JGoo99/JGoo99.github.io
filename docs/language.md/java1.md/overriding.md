---
layout: default
title: 오버라이딩
parent: Java 기초
grand_parent: Language
nav_order: 18
---

# XVII. 오버라이딩

---

## 1. 정의

> 상위 클래스에서 상속받은 매소드를 새롭게 재정의한다

---

## 2. 사용법

> 상위 클래스에 같은 매소드 명으로 재정의하면 하위클래스의 매소드로 호출된다

```java
class Cal{
  //생성자 생략	
  public void sum() {
    System.out.println( this.left + this.right );
  }
}

class diviCal extends Cal {
  //생성자 생략	
  public void sum() {
    System.out.println( "결과는 " + (this.left + this.right) + "입니다");
  }
	
public class test {
	
  public static void main(String[] args) {
		
    diviCal c1 = new diviCal(20, 10);
    c1.sum();
  }
}
```

```java
결과는 30입니다
```
---

## 3. 조건

- **동일한 서명(signature)**

> 상위-하위 클래스의 오버라이딩 매소드는 동일한 형식으로 정의해야 한다
>
> 1. 매소드의 이름
>
> 2. 매소드 매개변수의 숫자, 데이터 타입 그리고 순서
>
> 3. 매소드의 리턴 타입

<br/>

> 상위클래스와 다른 서명으로 재정의해보자

_상위클래스_

```java
class Cal {
  int left, right;
	
  public Cal(int left, int right) {
    this.left = left;
    this.right = right;
  }
	
  public void subtraction() {
    System.out.println( this.left - this.right );
  }
}
```

_하위클래스_

```java
class diviCal extends Cal {
	
  public diviCal(int left, int right) {
    super(left, right);
  }
	
  public int subtraction() {
    return ( this.left - this.right );
  }
}

public class test_sub {
  public static void main(String[] args) {
	
    diviCal c1 = new diviCal(20, 10);
    System.out.println( c1.subtraction() );
  }
}
```

{: .warning-title }
> Error
>
> The return type is incompatible with Cal.subtraction()
>
> 하위 클래스의 매소드(int)가 상위 클래스의 매스드(void)와 리턴 형식이 다름

<br/>

- 해결방법

> 부모클래스의 데이터타입 수정 _아래 참고_
>
> ~~사실 부모클래스를 수정하는 것은 좋지 않은 방법임~~

_상위클래스의 뺄셈 매소드_

```java
public int subtraction() {
  retrun ( this.left - this.right );
}
```

<br/>

{: .new-title }
> 중복의 제거
>
> 위 예시처럼 하위클래스가 부모클래스의 코드와 중복되는 것은 불필요하다
>
> 하위클래스의 오버라이딩 매소드를 아래처럼 수정하여 간단하게 중복을 피할 수 있다

_하위클래스의 뺄셈 매소드_

```java
public int subtraction() {
  return super.subtraction();
}
```

---

## **이 개념을 왜 배울까?**

{: .highlight }
> 하위클래스를 통해 상위클래스를 변경할 수 있다

> 상위클래스에서 수정하고싶은 매소드를 하위클래스에 overriding한 뒤
>
> 일부 수정작업이나 특정 코드를 추가할 수 있다

---

[Link button](https://opentutorials.org/course/1223/6090){: .btn .btn-outline }
