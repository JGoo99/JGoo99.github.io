---
layout: default
title: 조건문
parent: Algorithm
grand_parent: Language
nav_order: 3
has_children: true
---


_2023.04.21~_

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

# 조건문
{: .no_toc }

---

## #문제_1330

> 두 정수 A와 B가 주어졌을 때, A와 B를 비교하는 프로그램을 작성하시오.
>
> -10,000 ≤ A, B ≤ 10,000

---

### #입력
{: .no_toc }

> 1, 2

> 10, 2

> 5, 5

### #출력
{: .no_toc }

> <

> \>

>  ==


### #알고리즘 분류
{: .no_toc }

> 구현

---

### #풀이

```java
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
	  
    Scanner sc = new Scanner(System.in);
		
    short A = sc.nextShort();
    short B = sc.nextShort();
		
    if (A > B) System.out.println(">");
    if (A < B) System.out.println("<");
    if (A == B) System.out.println("==");
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 제한된 데이터 범위

> 제시된 데이터의 조건은 아래와 같다
>
> 1. 정수
>
> 2. -10,000 ≤ A, B ≤ 10,000
>
> 따라서 해당 범위에 들면서 메모리를 가장 적게 사용하는 **short형**을 사용한다
>
> _데이터 타입의 저장 범위를 정리해둔 링크를 아래에 첨부한다_

[Link button](https://jgoo99.github.io/docs/programing.md/java.md/data_type/#ii-%EB%B3%80%EC%88%98-%EC%84%A4%EC%A0%95-%EB%B0%A9%EB%B2%95){: .btn .btn-outline }

<br/><br/><br/>

## #문제_9498

> 시험 점수를 입력받아 등급을 출력하는 프로그램을 작성하시오.
>
> 90 ~ 100점 : A
> 
> 80 ~ 89점 : B
>
> 70 ~ 79점 : C
>
> 60 ~ 69점 : D
>
> 59점 이하 : F

---

### #입력
{: .no_toc }

> 100

### #출력
{: .no_toc }

> A


### #알고리즘 분류
{: .no_toc }

> 구현

---

### #풀이

```java
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
	  
    Scanner sc = new Scanner(System.in);
    Short score = sc.nextShort();
		
    if (score >= 90) 
      System.out.println("A");
    else if (score >= 80)
      System.out.println("B");
    else if (score >= 70)
      System.out.println("C");
    else if (score >= 60)
      System.out.println("D");
    else
      System.out.println("F");
		
    sc.close();
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> **논리연산자** vs **else if**

> 이 문제를 보았을 때 아래의 두 가지 풀이가 생각났다

<br/>

1. if문을 각각 작성하여 논리연산자 사용하기

```java
if (score >= 90) 
  System.out.println("A");
if (score >= 80 && score <= 89)
  System.out.println("B");
if (score >= 70 && score <= 79)
  System.out.println("C");
if (score >= 60 && score <= 69)
  System.out.println("D");
if (score <= 59)
  System.out.println("F");
```

<br/>

{:style="counter-reset:none"}
2. else if문을 활용하기

```java
if (score >= 90) 
  System.out.println("A");
else if(score >= 80)
  System.out.println("B");
else if (score >= 70)
  System.out.println("C");
else if (score >= 60)
  System.out.println("D");
else
  System.out.println("F");
```

<br/>

> 정답은 없지만 **코드의 중복**을 없애고 **가독성**을 높여주며 **유지보수**가 좋은
>
> 2번 **else if문을 활용하기**를 택했다
>
> _참고로 논리연산자를 정리했던 링크를 아래에 첨부한다_


[Link button](https://jgoo99.github.io/docs/programing.md/java.md/operator/#4-%EB%85%BC%EB%A6%AC-%EC%97%B0%EC%82%B0%EC%9E%90){: .btn .btn-outline }

<br/><br/><br/>

## #문제_2753

> **연도가 주어졌을 때, 윤년이면 1, 아니면 0을 출력하는 프로그램을 작성하시오.**

<br/>

> 윤년은 연도가 4의 배수이면서, 100의 배수가 아닐 때 또는 400의 배수일 때이다.
>
> 예를 들어, 2012년은 4의 배수이면서 100의 배수가 아니라서 윤년이다.
>
> 1900년은 100의 배수이고 400의 배수는 아니기 때문에 윤년이 아니다.
>
> 2000년은 400의 배수이기 때문에 윤년이다.

<br/>

> _연도는 1보다 크거나 같고, 4000보다 작거나 같은 자연수이다._

---

### #입력
{: .no_toc }

> 2000

> 1999

### #출력
{: .no_toc }

> 1

> 0

### #알고리즘 분류
{: .no_toc }

> 수학, 구현, 사칙연산

---

### #풀이

```java
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
	  
    Scanner sc = new Scanner(System.in);
    Short year = sc.nextShort();
		
    if (year%4 == 0 && year%100 != 0 || year%400 == 0)
      System.out.println("1");
    else 
      System.out.println("0");
		
    sc.close();
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 논리연산자의 우선순위

> 위의 쓰인 조건은 아래와 같다

```java
(year%4 == 0 && year%100 != 0 || year%400 == 0)
```

<br/>

> 자바는 위 조건을 어떤 순서로 해석할까?
>
> and 가 or 보다 우선순위이므로 아래의 순서대로 해석한다
>
> 1. year%4 == 0 && year%100 != 0
>
> 2. 또는 year%400 == 0
>
> _논리연산자의 우선순위를 정리한 링크를 아래에 첨부한다_

[Link button](https://jgoo99.github.io/docs/programing.md/java.md/operator/#5-%EA%B8%B0%EB%B3%B8%EC%97%B0%EC%82%B0%EC%9E%90%EC%9D%98-%EC%9A%B0%EC%84%A0%EC%88%9C%EC%9C%84){: .btn .btn-outline }

<br/><br/><br/>