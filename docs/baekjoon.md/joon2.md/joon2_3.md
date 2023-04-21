---
layout: default
title: 윤년
parent: 조건문
grand_parent: 백준 문제풀이
nav_order: 4
---

# 조건문

---

## #문제_2753

> **연도가 주어졌을 때, 윤년이면 1, 아니면 0을 출력하는 프로그램을 작성하시오.**
>
> 윤년은 연도가 4의 배수이면서, 100의 배수가 아닐 때 또는 400의 배수일 때이다.
>
> 예를 들어, 2012년은 4의 배수이면서 100의 배수가 아니라서 윤년이다.
>
> 1900년은 100의 배수이고 400의 배수는 아니기 때문에 윤년이 아니다.
>
> 2000년은 400의 배수이기 때문에 윤년이다.
>
> _연도는 1보다 크거나 같고, 4000보다 작거나 같은 자연수이다._

---

### #입력

> 2000

> 1999

### #출력

> 1

> 0

### #알고리즘 분류

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

{: .highlight }
> 논리연산자의 우선순위

> 위의 쓰인 조건은 아래와 같다

```java
(year%4 == 0 && year%100 != 0 || year%400 == 0)
```

> 자바는 이 조건을 어떤 순서로 해석할까?
>
> &&가 ||보다 우선순위이므로 아래의 순서대로 해석한다
>
> 1. year%4 == 0 && year%100 != 0
>
> 2. year%400 == 0
>
> _논리연산자의 우선순위를 정리한 링크를 아래에 첨부한다_

[Link button](https://jgoo99.github.io/docs/programing.md/java.md/operator/#5-%EA%B8%B0%EB%B3%B8%EC%97%B0%EC%82%B0%EC%9E%90%EC%9D%98-%EC%9A%B0%EC%84%A0%EC%88%9C%EC%9C%84){: .btn .btn-outline }