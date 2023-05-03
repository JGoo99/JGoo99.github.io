---
layout: default
title: 반복문
parent: Algorithm
grand_parent: Language
nav_order: 4
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

# 반복문
{: .no_toc }

---

## #문제_2739

> N을 입력받은 뒤, 구구단 N단을 출력하는 프로그램을 작성하시오. 출력 형식에 맞춰서 출력하면 된다.

---

### #입력
{: .no_toc }

> 2

### #출력
{: .no_toc }

> 2 * 1 = 2
>
> 2 * 2 = 4
>
> 2 * 3 = 6
> 
> 2 * 4 = 8
>
> 2 * 5 = 10
>
> 2 * 6 = 12
> 
> 2 * 7 = 14
>
> 2 * 8 = 16
>
> 2 * 9 = 18


### #알고리즘 분류
{: .no_toc }

> 수학, 구현

---

### #풀이
{: .no_toc }

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    byte N = sc.nextByte();

    for (int i = 1; i<10; i++) {
      System.out.println( N + " * " + i + " = " + (N*i) );
    }
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 변수의 중복

> Scanner의 객체명을 i로 지정했을 경우 for에서 자주쓰이는 변수 i와 겹친다
>
> 따라서 간단한 코드 작성 시에도 변수명을 미리 계획하고 생각하는 습관을 기르자

<br/><br/><br/>

## #문제_10950

> 두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.

---

### #입력
{: .no_toc }

> 5
>
> 1 1
>
> 2 3
>
> 3 4
>
> 9 8
>
> 5 2

### #출력
{: .no_toc }

> 2
>
> 5
>
> 7
>
> 17
>
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
    byte A, B, inCase;

    Scanner sc = new Scanner(System.in);
    inCase = sc.nextByte();

    for (byte i = 0; i < inCase; i++) {
      A = sc.nextByte();
      B = sc.nextByte();
      System.out.println(A+B);
    }
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
    byte A, B, inCase;

    Scanner sc = new Scanner(System.in);
    inCase = (byte) (sc.nextByte()+1);

    for (byte i = 0; i < inCase; i++) {
      A = sc.nextByte();
      B = sc.nextByte();
      System.out.println(A+B);
    }
  }
}
```

<br/>

- **WHY** : 왜 틀렸는가

> 반복 횟수가 1만큼 더 많기 때문에 런타임 에러가 떴다

<br/>

- **HOW** : 어떻게 풀어야하는가

> inCase 변수를 사용하여 1만큼 더 더해주었는데 i는 0부터 시작하기 때문에 더해줄 필요가 없다
>
> 따라서 더하거나 빼는 과정 없이 sc.nextByte()만 받아도 된다

```java
byte inCase = sc.nextByte();
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 사칙연산을 한 변수

> byte A = 3+inCase;
>
> 위의 경우 에러가 발생한다 따라서 아래처럼 선언해야 한다
>
> byte A = (byte) (3+inCase);

<br/><br/><br/>

## #문제_8393

> n이 주어졌을 때, 1부터 n까지 합을 구하는 프로그램을 작성하시오.

---

### #입력
{: .no_toc }

> 3

### #출력
{: .no_toc }

> 6

### #알고리즘 분류
{: .no_toc }

> 수학, 구현

---

### #풀이
{: .no_toc }

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    int sum=0, n;
    Scanner sc = new Scanner(System.in);
    n = sc.nextInt();

    for (int i=1; i < (n+1); i++) {
      sum = (int) (sum + i);
    }
    System.out.println(sum);
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> sum += i;

> sum = (int) (sum+i);
>
> 위의 문장은 아래 문장과 정확히 동일하다
>
> sum += i;

<br/><br/><br/>