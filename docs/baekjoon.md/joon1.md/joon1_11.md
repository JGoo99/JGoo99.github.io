---
layout: default
title: A+B+C
parent: 입출력과 사칙연산
grand_parent: 백준 문제풀이
nav_order: 12
---

# 입출력과 사칙연산

---

## #문제_11382

> 꼬마 정민이는 이제 A + B 정도는 쉽게 계산할 수 있다. 이제 A + B + C를 계산할 차례이다!
>
> A, B, C ( 1 ≤ A, B, C ≤ 10^12 )

---

### #입력

> 77, 77, 7777

### #출력

> 7931

### #알고리즘 분류

> 수학, 구현, 사칙연산

---

### #풀이

```java
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
	  
    Scanner sc = new Scanner(System.in);
		
    long A = sc.nextLong();
    long B = sc.nextLong();
    long C = sc.nextLong();
    //int형보다 더 큰 값이 입력될 수도 있음
		
    System.out.println( A+B+C );
		
    sc.close();
  }
}
```

---

### #오답노트

<br/>

- 나의 제출 답안

```java
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
	  
    Scanner sc = new Scanner(System.in);
		
    int A = sc.nextInt();
    int B = sc.nextInt();
    int C = sc.nextInt();
		
    System.out.println( A+B+C );
		
    sc.close();
  }
}
```

<br/>

- **WHY** : 왜 틀렸는가

> 입력받는 데이터타입을 저장 가능 범위에 못 미치는 int형으로 선언했다
>
> 이클립스에서는 잘 돌아갔으나, 제출 조건에 어긋나므로 런타임 에러가 떴다
>
> **Error : 런타입에러(InputMisMatch)**

<br/>

- **HOW** : 어떻게 풀어야하는가

> 제시된 문제에는 주어지는 데이터 범위가 10^12까지 이므로
>
> long타입으로 선언해야한다

```java
int A = sc.nextInt();   //런타임 에러 (input mismatch)
long A = sc.nextLong(); //에러 해결
```

---

### #유의할 점

{: .highlight }
> 정수형 데이터타입의 구분

> 정수 데이터 타입 : byte, short, int, long
>
> 차이점 : 저장 가능 범위, 메모리 크기

> 위에서 10^12까지의 범위가 수용가능해야 하므로 int형이 아닌 long타입을 사용해야한다
>
> _이전 수업에서 배웠던 데이터타입 링크를 아래에 첨부한다_


[Link button](https://jgoo99.github.io/docs/programing.md/java.md/data_type/#ii-%EB%B3%80%EC%88%98-%EC%84%A4%EC%A0%95-%EB%B0%A9%EB%B2%95){: .btn .btn-green }