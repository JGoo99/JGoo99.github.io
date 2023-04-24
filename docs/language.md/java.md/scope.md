---
layout: default
title: 유효범위
parent: Java
grand_parent: Language
nav_order: 14
---

# XIII. 유효범위

---

## 1. 출현 배경

_디렉토리의 출현 배경과 유사하다_

<br/>

- **디렉토리의 출현 배경**

> 파일의 양이 많아지면서 파일명 중복 오류 발생
>
> 다른 디렉토리에 있다면 같은 파일명이라도 오류 발생 x

<br/>

- **유효범위의 출현 배경**

> 매소드와 클래스 또한 디렉토리와 비슷한 맥락에서 출현하게 되었다
>
> 전역 변수들끼리의 충돌로 인한 오류 발생
>
> 매소드와 클래스를 이용해 유효범위를 정하고 전역변수/지역변수를 사용한다

---

## 2. 변수의 유효범위

### i. 전역변수

```java
public class test {
  static int i ; 
  //전역변수 선언
}
```

> 클래스 내부, 모든 중괄호 안의 변수에 공유된다

<br/>

### ii. 지역변수

```java
public class test {
  public void A() {
    int i;
    //지역변수 선언
  }
}
```

> 해당 매소드의 중괄호 안에서만 공유된다
>
> _아래 예시를 통해 알아보자_

---

## 3. 클래스의 유효범위

### i. 정적인 유효범위

> _자바가 채택하고 있는 방식은 **정적인 유효범위** 이다_
> 
> 정적인 유효범위 : 매소드 내의 지역변수 or 소속 클래스의 전역변수

```java
public class test {
  static int i = 10;
  //전역변수 i
	
  static void a() {
    int i = 5;
    //매소드 a에서만 유효한 지역변수 i
    b();
  }
	
  static void b() {
    System.out.println(i);
    //전역변수 i
  }
	
  public static void main(String[] args) {
    a();
  }
}
```

{: .highlight-title }
> 🤔
>
> 결과를 보기 전에 먼저 여러가지 가능성을 생각해보자

<br/>

{: .highlight }
> 첫째, 매소드 a의 지역 변수가 호출될 것이다

> 메인이 실행되면서 매소드 a가 호출되고
>
> 매소드 a 내에서 b가 호출되는 것이기 때문에
>
> 매소드 b 에서 프린트되는 i는 a의 지역변수 int i = 5 일 것이다

<br/>

{: .highlight }
> 둘째, 매인 매소드의 전역 변수가 호출될 것이다

> 매인 매소드에서 매소드 a를 호출한 것이기 때문에
>
> 매인 매소드에서 가져오는 전역변수 static int i = 10 일 것이다

<br/>

{: .highlight }
> 셋째, 최종 단계인 매소드 b의 전역변수가 호출될 것이다

> 클래스 매소드 b에서 읽어드릴 수 있는 멤버는 전역 변수이다
> 
> 따라서 전역변수인 static int i = 10 일 것이다

<br/>

{: .important-title }
> 세번째 정답 !!
>
> 최종 단계인 클래스 매소드 b 내에서 가져온 전역변수 i가 출력된 것

```java
static void b() {
  int i =7;
  System.out.println(i);
}
```
```java
7
```

{: .important-title }
> 🥕
>
> 매소드 내에서 지역 변수를 선언했더니 7이 출력된 것을 알 수 있다

---

### ii. 변수의 충돌

> 매소드 내부에서 동일한 변수 선언으로 인해 반복문이 제대로 작동하지 않는 경우

```java
public class test {
  static int i;
  //전역변수 i
	
  static void a() {
    i = 0;
    //전역변수 i
    //계속 0으로 초기화 되는 문제발생 
  }
	
  public static void main(String[] args) {
    for(i = 0; i < 5; i++) {
      //전역변수 i
      a();
      System.out.println(i);
    }
  }
}
```

{: .warning-title }
> 프린트 무한반복
>
> 전역변수(i)가 a()매소드에서 계속 0으로 초기화됨
>
> 0 무한출력

<br/>

- 해결방법

> 1. 메인에서 지역변수로 선언하기
>
> 2. 클래스 매소드의 변수를 지역변수로 바꾸기
>
> _아래 코드로 확인해보자_

<br/>

1. 메인에서 지역변수로 선언하기

```java
public static void main(String[] args) {
  for(int i = 0; i < 5; i++) {
    a();
    System.out.println(i);
  }
}
```

> 메인 매소드 내에서의 지역변수 i는 클래스 변수 i와 다르기 때문에
>
> 영향을 받지 않고 정상출력이 가능하다

<br/>

{:style="counter-reset:none"}
2. 클래스 매소드의 변수를 지역변수로 바꾸기

```java
public void a() {
  int i = 0;
}
```

> 클래스 매소드 a() 에서 선언된 지역변수는 해당 매소드의 안에서만 유효
>
> 따라서 매인 매소드의 클래스 변수 i는 영향없이 정상 출력

---

## 4. 인스턴스의 유효범위

> 클래스의 유효범위와 거의 동일하지만 결정적인 차이점은 **this** 에 있다

```java
class This {
  int k = 7;
	
  void print() {
    int k = 4;
    //전역변수보다 우선순위가 높음
    System.out.println(k); //print()의 지역변수 k
    System.out.println(this.k); //객체 c1의 클래스 변수 k
  }
}

public class test {
	
  public static void main(String[] args) {
		
    This c1 = new This();
    c1.print();
  }
}
```

```java
4
7
```

{: .highlight }
> this의 의미

> 인스턴스(c1) 자신을 가르킴
>
> 인스턴스 매소드 print()에서 인스턴스 전역 변수 k(=7)에 접근

---

## **In My Opinion**

{: .highlight }
> 바람직한 유효범위에 대하여

> 인스턴스 매소드에서 전역 인스턴스 변수를 많이 사용하는 것은 좋지 않다
>
> 해당 매소드에 영향을 미치는 매개 변수임을 알기 어렵기 때문에
>
> 코드의 가독성을 떨어뜨린다 _아래 참고_

```java
class A {
  int a;

  void C(int c) {
    System.out.println(this.a);
    //c를 사용할 것은 미리 알고 있지만
    //전역변수 a를 사용할 것은 읽어봐야 알 수 있음 
  } 
}
```

---

## **이 개념을 왜 배울까?**

{: .highlight }
> 변수 접근 방법과 충돌 방지를 위해

> 각 변수가 어떤 소속인지 정확히 알고
>
> 어떻게 접근해야 하는지, 어떻게 선언해야 변수 중복을 막을 수 있는지 알아야
>
> 클래스와 매소드를 올바르게 사용할 수 있다

---

[Link button](https://opentutorials.org/course/1223/5440){: .btn .btn-outline }

