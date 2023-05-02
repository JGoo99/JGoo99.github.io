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

# 조건문
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
