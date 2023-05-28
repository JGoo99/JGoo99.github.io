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

## #문제_10871

> 정수 N개로 이루어진 수열 A와 정수 X가 주어진다. 이때, A에서 X보다 작은 수를 모두 출력하는 프로그램을 작성하시오.

---

### #입력
{: .no_toc }

> 10 5
>
> 1 10 4 9 2 3 8 5 7 6

### #출력
{: .no_toc }

> 1 4 2 3


### #알고리즘 분류
{: .no_toc }

> 구현

---

### #풀이
{: .no_toc }

1. **Scanner 이용**

```java
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    int[] A = new int[sc.nextInt()];
    int X = sc.nextInt();

    for (int i = 0; i < A.length; i++) {
      A[i] = sc.nextInt();
    }

    for (int i = 0; i < A.length; i++) {
      if (A[i] < X) {
        System.out.print(A[i] + " ");
      }
    }
  }
}
```

<br/>

{:style="counter-reset:none"}
2. **Buffered 이용**

> 메모리와 시간절약 가능

```java
import java.io.*;

class Main {
  public static void main(String[] args) throws IOException {
    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));

    String input1 = br.readLine();
    String[] word = input1.split(" ");

    int N = Integer.parseInt(word[0]);
    int X = Integer.parseInt(word[1]);

    int[] A = new int[N];

    String input2 = br.readLine();
    String[] num = input2.split(" ");
    br.close();

    for (int i = 0; i < N; i++) {
      A[i] = Integer.parseInt(num[i]);
      if (A[i] < X) {
        bw.write(A[i] + " ");
      }
    }
    bw.flush();
    bw.close();
  }
}
```

![joon4_1](https://github.com/JGoo99/JGoo99.github.io/assets/126454114/79b47eed-09e9-4407-ac95-1d3285169e9c)

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 반복문의 효율성

> 하나의 반복문에서 여러가지 수행을 할 수 있다면 더욱 효율적일 것이다
>
> 따라서 같이 반복할 수 있는 두 가지 문장을 서로다른 반복문에 넣어 효율성을 떨어뜨리는 일은 없도록 하자

<br/>

{: .highlight }
> buffered와 split

> BufferedReader로 한줄의 여러 정수를 입력받았을 때, 띄어쓰기를 기준으로 배열저장하기

```java
String input = br.readLine();
String[] arr = input.split(" ");
```

<br/><br/><br/>

---