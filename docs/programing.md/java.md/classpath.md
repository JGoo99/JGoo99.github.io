---
layout: default
title: 클래스패스
parent: Java
grand_parent: Programing
nav_order: 20
---

# XIX. 클래스패스

---

## 1. 정의

### i. 클래스 패스

> iterm에서 실행할 때 클래스가 위치하는 경로를 지정하는 것 

### ii. 컴파일

> java로 작성한 코드를 컴퓨터가 이해할 수 있는 이진법 언어로 변환하는 것
>
> 두개의 클래스를 가진 소스코드를 컴파일해보자

1. 새로운 소스파일을 생성한다 (파일명: srcbin)

//이미지 삽입 예정

{:style="counter-reset:none"}
2. 소스파일 내에 텍스트 편집기를 이용하여 클래스를 생성한다

_클래스 소스_

```java
class item {}

public class classpthDemo {}
```

> 하나의 소스에 두개의 클래스가 존재한다

{:style="counter-reset:none"}
3. iterm2: 패키지 내에서 **ls -al** 로 디렉토리 리스트를 확인한다

//이미지 삽입 예정

{:style="counter-reset:none"}
4. iterm2: **javac classpthDemo.java** 로 자바 소스코드를 컴파일한다

{:style="counter-reset:none"}
5. iterm2: **ls -al** 로 디렉토리 리스트를 확인한다

//이미지 삽입 예정

> 새로 생성된 파일
>
> **classpthDemo.class ,  item.class**
>
> 하나의 소스코드라도 각 클래스는 따로 컴파일된다

---

## 2. 사용법

### i. 자바 소스 생성 및 컴파일

1. 두 개의 클래스를 가진 소스코드 생성

_소스코드 srcbin-**classpathDemo2.java**_

```java
class item {
  public void print() {
    System.out.println("hello world");
  }
}

public class classpthDemo {
  public static void main(String[] args) {
    item i1 = new item();
    i1.print();
  }
}
```

{:style="counter-reset:step-counter 1"}
2. iterm에서 컴파일하여 각각의 클래스 파일 생성

//이미지 삽입 예정

### ii. iterm 에서 실행

> 같은 디렉토리 내에 두 클래스가 존재하는 경우


* srcbin 폴더로 이동하여 실행

//이미지 삽입 예정

{: .important-title }
> 실행 시 주의할 점
>
> 1. srcbin로 이동해야 함
>
> 2. 클래스명(확장자x) 로 입력해야 함
>
> _(패키지가 있으면 **패키지명.클래스명**으로 입력)_ 

{: .highlight-title }
> 🧐
>
> 만약 item클래스가 다른 디렉토리에 있다면?
>
> 이때 필요한 것이 **classpath** 이다

---

> 다른 디렉토리 내에 각 클래스가 존재하는 경우 **classpath**

//이미지 삽입 예정

```
java -classpath ".:lib" classpathDemo
```

---

## **이 개념을 왜 배울까?**

{: .highlight }
> 클래스

>
>
>

---

[Link button](https://opentutorials.org/course/1223/5527){: .btn .btn-outline }
