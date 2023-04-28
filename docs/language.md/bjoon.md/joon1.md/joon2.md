---
layout: default
title: 조건문
parent: Algorithm
grand_parent: Language
nav_order: 3
has_children: true
---

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
{: .no_toc }

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
{: .no_toc }

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
{: .no_toc }

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

## #문제_14681

> **점의 좌표를 입력받아 그 점이 어느 사분면에 속하는지 알아내는 프로그램을 작성하시오.**

<br/>

> (−1000 ≤ x ≤ 1000; x ≠ 0) 
>
> (−1000 ≤ y ≤ 1000; y ≠ 0)

---

### #입력
{: .no_toc }

> 12, 5

> 9, -13

### #출력
{: .no_toc }

> 1

> 4

### #알고리즘 분류
{: .no_toc }

> 구현, 기하학

---

### #풀이
{: .no_toc }

```java
import java.util.Scanner;

public class Main {

  public static void main(String[] args) {
    Short x,y;
		
    Scanner i = new Scanner(System.in);
    x = i.nextShort();
    y = i.nextShort();
		
    if (x>0) {
      if (y>0) {
        System.out.println(1);      //x>0, y>0
      } else System.out.println(4); //x>0, y<0
    } else {
      if (y>0) {
        System.out.println(2);      //x<0, y>0
      } else System.out.println(3); //x<0, y<0
    }
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 조건문의 중첩될수록 복잡해진다

> 가독성을 위해 주석을 작성하거나 더 간단한 코드를 모색한다
>
> 위의 경우 논리연산자 and를 사용하여 4줄의 syso으로 표현해도 정답이 된다

```java
import java.util.Scanner;

public class Main {

  public static void main(String[] args) {
    Short x,y;
		
    Scanner i = new Scanner(System.in);
    x = i.nextShort();
    y = i.nextShort();
		
    if (x>0 && y>0) System.out.println(1);
    if (x>0 && y<0) System.out.println(4);
    if (x<0 && y>0) System.out.println(2);
    if (x<0 && y<0) System.out.println(3);
  }
}
```

<br/><br/><br/>

## #문제_2884

> **상근이가 설정한 알람 시각이 주어졌을 때, '45분 일찍 맞추기' 방법을 사용한다면, 이를 언제로 고쳐야 하는지 구하는 프로그램을 작성하시오.**

<br/>

>  (0 ≤ H ≤ 23, 0 ≤ M ≤ 59) 

---

### #입력
{: .no_toc }

> 10 10

> 0 30

> 23 40

### #출력
{: .no_toc }

> 9 25

> 23 45

> 22 55

### #알고리즘 분류
{: .no_toc }

> 수학, 사칙연산

---

### #풀이
{: .no_toc }

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    byte H, M;

    Scanner i = new Scanner(System.in);
    H = i.nextByte();
    M = i.nextByte();

    if (M-45 >= 0) System.out.println( H + " " + (M-45) ); 
    //45분을 빼도 H가 바뀌지 않는 경우
    if (M-45 < 0) {
    //45분을 빼면 H가 바뀌는 경우
      if (H == 0) {
        System.out.println(23 + " " + (M + 15));
        //00시일 경우
      } else System.out.println((H - 1) + " " + (M + 15));
        //00시가 아닌 경우
    }
  }
}
```

---

### #오답노트

<br/>

- 나의 제출 답안

```java
if (M-45 > 0) System.out.println( H + " " + (M-45) ); 
//이 부분이 다름
  if (M-45 < 0) {
    if (H == 0) {
      System.out.println(23 + " " + (M + 15));
    } else System.out.println((H - 1) + " " + (M + 15));
  }
}
```

<br/>

- **WHY** : 왜 틀렸는가

> 크다, 작다를 기준으로 생각하다보니 M-45가 0이 되는 경우를 미쳐 생각하지 못했다

<br/>

- **HOW** : 어떻게 풀어야하는가

> 45분을 제할 경우 나올 수 있는 모든 경우를 생각해본다
>
> M-45 == 0 인 경우, H에 변화가 없어도 되므로 첫째 조건을 **크거나 같다로 수정**한다

```java
if (M-45 >= 0) System.out.println( H + " " + (M-45) ); 
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 조건문에서 모든 경우의 수를 생각해보자

> 좋은 코드는 예외까지 고려할 수 있는 코드이다
>
> 입력값이 들어왔을 때 빠져나갈 구멍이 없도록 만들자

<br/>

{: .highlight }
> Scanner의 구분자

> Scanner는 입력받은 값이 여러개인 경우, 스페이스바를 기준으로 구분한다
>
> 따라서 위의 경우, H와 M을 엔터 기준으로 입력해도 되고 스페이스바를 이용하여 한 번에 입력해도 된다

- 입력 콘솔창

> 23 40

or

> 23
>
> 40


<br/><br/><br/>

## #문제_10699

> 서울의 오늘 날짜를 출력하는 프로그램을 작성하시오.

---

### #입력
{: .no_toc }

> 없음

### #출력
{: .no_toc }

> 2023-04-27

### #알고리즘 분류
{: .no_toc }

> 구현

---

### #풀이
{: .no_toc }

```java
import java.text.SimpleDateFormat;
import java.util.Date;

public class Main {
  public static void main(String[] args) {
    Date date = new Date();
    SimpleDateFormat formatter = new SimpleDateFormat("yyyy-MM-dd");

    System.out.println(formatter.format(date));
  }
}
```

---

### #참고
{: .no_toc }

{: .highlight }
> 현재시간을 출력

> 아래에 현재시간을 출력할 수 있는 다양한 방법에 대해 소개하고있다 _링크 첨부_

[Link button](https://developer-talk.tistory.com/408){: .btn .btn-outline }

<br/><br/><br/>

## #문제_2420

> **두 서브도메인의 유명도가 주어졌을 때, 그 차이를 구하는 프로그램을 작성하시오.**

<br/>

>  (-2,000,000,000 ≤ N, M ≤ 2,000,000,000)

---

### #입력
{: .no_toc }

> -2, 5

### #출력
{: .no_toc }

> 7

### #알고리즘 분류
{: .no_toc }

> 수학, 구현, 사칙연산

---

### #풀이
{: .no_toc }

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    long N, M;

    Scanner i = new Scanner(System.in);
    N = i.nextLong();
    M = i.nextLong();

    if (N-M >= 0) {
      System.out.println(N-M);
    } else System.out.println(M-N);
  }
}
```

---

### #오답노트

<br/>

- 나의 제출 답안

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    int N, M;

    Scanner i = new Scanner(System.in);
    N = i.nextInt();
    M = i.nextInt();

    if (N-M >= 0) {
      System.out.println(N-M);
    } else System.out.println(M-N);
  }
}
```

<br/>

- **WHY** : 왜 틀렸는가

> 두 정수의 범위는 int형에 속하므로 데이터 타입과 스캐너입력값의 타입을 int로 선언했다

<br/>

- **HOW** : 어떻게 풀어야하는가

> 두 정수의 덧셈, 뺄셈 과정에서 int형의 데이터 저장 범위를 넘어설 수 있다
>
> int형끼리의 연산 시 int형으로 출력되기 때문에 아래와 같이 오류가 발생한다

```java
-2000000000 2000000000

294967296
```

> 따라서 ±4,000,000,000를 저장할 수 있는 long타입으로 선언해야 한다

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 변수의 데이터타입 선언은 계산값도 고려하기

> 해당 변수의 대입값 뿐만 아니라 연산값도 고려하여 선언해야 한다

<br/>

{: .highlight }
> 절대값 함수 사용하기

> 자바에서는 절대값을 도출하는 함수를 지원하고있다
>
> 아래와 같이 절대값 함수를 사용하여 값을 도출하는 방법도 있다

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    int N, M;

    Scanner i = new Scanner(System.in);
    N = i.nextInt();
    M = i.nextInt();

    if (N-M >= 0) {
      System.out.println(N-M);
    } else System.out.println(M-N);
  }
}
```

<br/><br/><br/>

## #문제_

> 

---

### #입력
{: .no_toc }

> 

> 

> 

### #출력
{: .no_toc }

> 

> 

>


### #알고리즘 분류
{: .no_toc }

> 

---

### #풀이
{: .no_toc }

```java

```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 

> 

<br/><br/><br/>