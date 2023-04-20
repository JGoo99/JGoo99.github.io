---
layout: default
title: 사칙연산
parent: 입출력과 사칙연산
grand_parent: 백준 문제풀이
nav_order: 7
---

# 입출력과 사칙연산

---

## #문제

> 두 자연수 A와 B가 주어진다. 이때, A+B, A-B, A*B, A/B(몫), A%B(나머지)를 순서대로 출력하는 프로그램을 작성하시오. 

---

### #입력

> 7 3

### #출력

> 10
>
> 4
>
> 21
>
> 2
>
> 1

### #알고리즘 분류

> 수학, 구현, 사칙연산

---

### #풀이

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
		
    Scanner i = new Scanner(System.in);
	  
    int A = i.nextInt();
    int B = i.nextInt();
	  
    System.out.println(A+B);
    System.out.println(A-B);
    System.out.println(A*B);
    System.out.println(A/B);
    System.out.println(A%B);
  }
}
```

---

### #유의할 점

{: .highlight }
> print() 와 println()의 차이

> print()
>
> 줄바꿈을 하지 않는 순수 프린트 명령어

> println()
>
> print + line 으로 자동 줄바꿈을 해주는 명령어
