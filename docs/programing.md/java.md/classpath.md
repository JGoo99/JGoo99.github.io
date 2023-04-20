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

<br/>

### ii. 컴파일

> java로 작성한 코드를 컴퓨터가 이해할 수 있는 이진법 언어로 변환하는 것
>
> 두개의 클래스를 가진 소스코드를 컴파일해보자  

<br/>

**1. 새로운 파일을 생성한다 (파일명: srcbin)**

![classpath1](https://user-images.githubusercontent.com/126454114/233028825-ada6f620-05d8-4a9f-999f-09107c6f5d23.jpg)  

<br/>

{:style="counter-reset:none"}
**2. 텍스트 편집기를 이용하여 소스코드를 생성한다**

_소스 코드_

```java
class item {}

public class classpthDemo1 {}
```

> 하나의 소스에 두개의 클래스가 존재하는 모습  

<br/>

{:style="counter-reset:none"}
**3. iterm2: srcbin 디렉토리 리스트를 확인한다**

![classpath2](https://user-images.githubusercontent.com/126454114/233028935-847daf79-d5eb-4601-814b-e50870ac40c9.jpg)

<br/>

{:style="counter-reset:none"}
**4. iterm2: classpathDemo1 자바 소스코드를 컴파일한다**

```
javac classpathDemo1.java
```

<br/>

{:style="counter-reset:none"}
**5. iterm2: 다시 srcbin 디렉토리 리스트를 확인한다**

![classpath3](https://user-images.githubusercontent.com/126454114/233029025-6b38b68e-070c-4471-883c-a37b4ffba2b7.jpg)


- 새로 생성된 파일

> **classpthDemo1.class ,  item.class**
>
> 여러개의 클래스가 하나의 소스코드 내에 있더라도 각각 컴파일된다

---

## 2. 사용법

### i. classpath를 사용하지 않는 경우

> classpath 명령어의 필요성을 알기 위해 classpath가 필요없는 경우를 먼저 알아보자

<br/>

**1. 두 개의 클래스를 가진 소스코드 생성**

_소스코드_

```java
class item {
  public void print() {
    System.out.println("Hello World");
  }
}

public class classpthDemo2 {
  public static void main(String[] args) {
    item i1 = new item();
    i1.print();
  }
}
```

<br/>

{:style="counter-reset:step-counter 1"}
**2. iterm에서 컴파일하여 각각의 클래스 파일 생성**

![classpath4](https://user-images.githubusercontent.com/126454114/233030513-cd2f359f-d5e1-4e43-a5ab-f277ae7e1d98.jpg)

<br/>

**3. srcbin 폴더로 이동하여 실행**

![classpath5](https://user-images.githubusercontent.com/126454114/233030609-45f73fea-7380-4e21-b709-50464bc97059.jpg)

<br/>

{: .important-title }
> 실행 시 주의할 점
>
> 1. srcbin로 이동해야 함
>
> 2. 클래스명(확장자x) 로 입력해야 함
>
> _(패키지가 있으면 **패키지명.클래스명**으로 입력)_ 

---

### ii. classpath를 사용해야하는 경우

> 만약 item클래스가 다른 디렉토리에 있다면?
>
> 이때 필요한 것이 **classpath** 이다

<br/>

**1. 하위파일을 만들어 item.class를 이동**

![classpath6](https://user-images.githubusercontent.com/126454114/233030681-5c5f3511-81a8-4e0f-ae15-ff0d6a9c875b.jpg)


> 두 클래스가 다른 디렉토리에 존재하는 모습

<br/>

**2. iterm 에서 실행**

![classpath7](https://user-images.githubusercontent.com/126454114/233030732-1d536021-f9d9-45b2-9928-4af32080c964.jpg)


{: .warning-title }
> Error
>
> Exception in thread "main" java.lang NoClassDefFoundError: item
>
> at classpathDemo2.main(classpathDemo2.java:9)
>
> 현재 srcbin 디렉토리에서 item클래스를 찾을 수 없어서 생기는 에러

**3. classapth 명령어 사용**

```
java -classpath ".:lib" classpathDemo
```

![classpath8](https://user-images.githubusercontent.com/126454114/233030799-bd023adc-065b-4592-bc02-7d9350e0951d.jpg)


---

- **".:lib"** 해석

{: .note-title }
> **.**
>
> 현재 디렉토리

{: .note-title }
> **;**
>
> 경로와 경로를 구분하는 구분자

{: .note-title }
> **lib**
>
> 현재 디렉토리(.)에 없다면 lib 디렉토리에서 찾는다

---

## **이 개념을 왜 배울까?**

{: .highlight }
> 프로젝트의 규모가 커질수록 중요한 개념이다

> 프로젝트의 규모가 커지고 협업자가 늘어나게 되면
>
> 그에 맞게 로직들을 체계적으로 관리해야한다
>
> 체계적으로 정리가 되어있는 로직들을 불러오는 과정에서 필연적으로
>
> 이번에 배운 classpath와 앞으로 알아갈 환경변수 개념을 알아야 한다

---

[Link button](https://opentutorials.org/course/1223/5527){: .btn .btn-outline }
