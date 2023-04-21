---
layout: default
title: 두 수 비교하기
parent: 조건문
grand_parent: 백준 문제풀이
nav_order: 2
---

# 조건문

---

## #문제_1330

> 두 정수 A와 B가 주어졌을 때, A와 B를 비교하는 프로그램을 작성하시오.
>
> -10,000 ≤ A, B ≤ 10,000

---

### #입력

> 1, 2

> 10, 2

> 5, 5

### #출력

> <

> \>

>  ==


### #알고리즘 분류

> 구현

---

### #풀이

```java
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
	  
    Scanner sc = new Scanner(System.in);
		
    short A = sc.nextShort();
    short B = sc.nextShort();
		
    if (A > B) System.out.println(">");
    if (A < B) System.out.println("<");
    if (A == B) System.out.println("==");
  }
}
```

---

### #유의할 점

{: .highlight }
> 제한된 데이터 범위

> 제시된 데이터의 조건은 아래와 같다
>
> 1. 정수
>
> 2. -10,000 ≤ A, B ≤ 10,000
>
> 따라서 해당 범위에 들면서 메모리를 가장 적게 사용하는 **short형**을 사용한다
>
> _데이터 타입의 저장 범위를 정리해둔 링크를 아래에 첨부한다_

[Link button](https://jgoo99.github.io/docs/programing.md/java.md/data_type/#ii-%EB%B3%80%EC%88%98-%EC%84%A4%EC%A0%95-%EB%B0%A9%EB%B2%95){: .btn .btn-outline }