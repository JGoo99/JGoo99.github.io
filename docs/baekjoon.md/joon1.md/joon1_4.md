---
layout: default
title: AxB
parent: 입출력과 사칙연산
grand_parent: 백준 문제풀이
nav_order: 5
---

# 입출력과 사칙연산

---

## #문제_10998

> 두 정수 A와 B를 입력받은 다음, A×B를 출력하는 프로그램을 작성하시오.

---

### #입력

> 1, 2

### #출력

> 2

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
		
    System.out.println(A*B);
  }
}
```

---

### #유의할 점

{: .highlight }
> 연산자의 개념을 확실히 하자

> 이전 수업에서 연산자 개념을 정리한 링크 버튼을 첨부한다

[Link button](https://jgoo99.github.io/docs/programing.md/java.md/operator/){: .btn .btn-purple }