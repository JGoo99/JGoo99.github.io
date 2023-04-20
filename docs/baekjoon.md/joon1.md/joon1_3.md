---
layout: default
title: A-B
parent: 입출력과 사칙연산
grand_parent: 백준 문제풀이
nav_order: 4
---

# 입출력과 사칙연산

---

## #문제

> 두 정수 A와 B를 입력받은 다음, A-B를 출력하는 프로그램을 작성하시오.

---

### #입력

> 3, 2

### #출력

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
		
    System.out.println(A-B);
  }
}
```

---

### #유의할 점

<br/>

{: .highlight }
> Scanner 입력의 데이터 타입을 확실히하자

> **정수를 받을 경우**
>
> int A = i.nextInt();

> **문자열을 받을 경우**
>
> String A = i.next();