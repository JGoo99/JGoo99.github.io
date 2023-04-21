---
layout: default
title: 나머지
parent: 입출력과 사칙연산
grand_parent: 백준 문제풀이
nav_order: 10
---

# 입출력과 사칙연산

---

## #문제_10430

> **세 수 A, B, C가 주어졌을 때, 아래의 네 가지 값을 구하는 프로그램을 작성하시오.**
>
> (A+B)%C는 ((A%C) + (B%C))%C 와 같을까?
>
> (A×B)%C는 ((A%C) × (B%C))%C 와 같을까?

---

### #입력

> 5, 8, 4

### #출력

> 1
>
> 1
>
> 0
>
> 0

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
    int C = i.nextInt();
	  
    System.out.println( (A+B) % C );
    System.out.println( ( (A%C) + (B%C) ) % C );
    System.out.println( (A*B) % C );
    System.out.println( ( (A%C) * (B%C) ) % C );
	  
    i.close();
  }
}
```

---

### #유의할 점

{: .highlight }
> Scanne(System.in) 닫기

> Scanner를 System.in 해주었다면 사용종료 후 꼭 닫아야한다
>
> 안 닫을 경우 아래와 같은 경고문이 뜬다
>
> Resource leak:'scanner' is never closed
> 
> **닫는 방법 : i.close();** 

