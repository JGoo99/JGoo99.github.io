---
layout: default
title: 배열
parent: Algorithm
grand_parent: Language
nav_order: 5
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

# 배열
{: .no_toc }

---

## #문제_10807

> 총 N개의 정수가 주어졌을 때, 정수 v가 몇 개인지 구하는 프로그램을 작성하시오.

---

### #입력
{: .no_toc }

> 11
>
> 1 4 1 **2** 4 **2** 4 **2** 3 4 4
>
> 2

### #출력
{: .no_toc }

> 3


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
    int N; //정수 개수
    int V; //세야할 변수
    int counter = 0; //정수v의 빈도수

    Scanner sc = new Scanner(System.in);
    N = sc.nextInt();
    int[] arr = new int[N];

    for (int i = 0; i < N; i++) {
      arr[i] = sc.nextInt();
    }

    V = sc.nextInt();

    for (int i = 0; i < arr.length; i++) {
      if (arr[i] == V) {
        counter++;
      }
    }
    System.out.println(counter);
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 1차원 배열의 종류

> 1차원 배열은 같은 자료형의 묶음이며 그 중에는 int형과 String형 등이 있다
>
> 위 문제에서 처음엔 String배열로 문제를 풀었는데 해당 문제는 int형으로 푸는 것이 효율적이다
>
> 따라서 상황에 맞게 알맞는 배열타입을 선언하는 것이 중요하다

<br/><br/><br/>

---