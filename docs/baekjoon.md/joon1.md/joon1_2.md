---
layout: default
title: A+B
parent: 입출력과 사칙연산
grand_parent: 백준 문제풀이
nav_order: 3
---

# 입출력과 사칙연산

---

## #문제_1000

> 두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.

---

### #입력

> 1, 2

### #출력

> 3

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
  }
}
```

---

### #유의할 점

{: .highlight }
> Scanner 사용법을 외워보자

> 이제는 이해를 넘어서서 사용법을 외워보자