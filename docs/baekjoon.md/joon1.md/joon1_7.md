---
layout: default
title: ??!
parent: 입출력과 사칙연산
grand_parent: 백준 문제풀이
nav_order: 8
---

# 입출력과 사칙연산

---

## #문제

> 준하는 사이트에 회원가입을 하다가 joonas라는 아이디가 이미 존재하는 것을 보고 놀랐다. 
>
> 준하는 놀람을 ??!로 표현한다. 
>
> 준하가 가입하려고 하는 사이트에 이미 존재하는 아이디가 주어졌을 때, 놀람을 표현하는 프로그램을 작성하시오. 

---

### #입력

> joonas

### #출력

> joonas??!

### #알고리즘 분류

> 수학, 구현, 사칙연산

---

### #풀이

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
	  
    Scanner i = new Scanner(System.in);
    System.out.println(i.next() + "??!");
  }
}
```

---

### #오답노트

- 나의 제출 답안

> 이미 존재하는 아이디를 배열로 저장한 후 입력받은 아이디와 같은 아이디가 있을 떄 
>
> 해당 아이디와 ??!를 출력하는 로직으로 풀었다

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
	  
    String[] member = {"goo", "jin", "joonas"};
		
    Scanner i = new Scanner(System.in);
    String ID = i.next();
	  
    for (String e : member) {
      if (ID.equals(e))
        System.out.println(ID + "??!");
    }
  }
}
```

<br/>

- WHY : 왜 틀렸는가

> "이미 존재하는 아이디" 라는 워딩에서 배열로 저장해야겠다고 생각했다

<br/>

- HOW : 어떻게 풀어야하는가

> 해당 문제는 간단한 입출력을 요구하는 문제임을 감안했을 때
>
> String으로 Scanner를 사용하는 방법 정도만 숙지하면 되는 문제였다


---

### #유의할 점

{: .highlight }
> 코드의 최적화

> Scanner로 입력받은 값을 문자열에 따로 저장한 후 출력하는 방법도 있지만
>
> 문자변수가 필요하지 않다면, 저장하지 않고 바로 출력할 수도 있다 
>
> _아래 참고_

<br/>

_문자열 저장 후 출력_

```java
Scanner i = new Scanner(System.in);
String ID = i.next();
System.out.println(ID + "??!");
```

_바로 출력_

```java
Scanner i = new Scanner(System.in);
System.out.println(i.next() + "??!");
```
