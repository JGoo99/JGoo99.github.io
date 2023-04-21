---
layout: default
title: A/B
parent: 입출력과 사칙연산
grand_parent: 백준 문제풀이
nav_order: 6
---

# 입출력과 사칙연산

---

## #문제_1008

> 두 정수 A와 B를 입력받은 다음, A/B를 출력하는 프로그램을 작성하시오.

---

### #입력

> 1, 3

### #출력

> 0.33333333333333333333333333333333
>
> _오차 허용_

### #알고리즘 분류

> 수학, 구현, 사칙연산

---

### #풀이

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
		
    Scanner i = new Scanner(System.in);
	  
    double A = i.nextDouble();
    double B = i.nextDouble();
	  
    System.out.println(A/B);
  }
}
```

---

### #유의할 점

{: .highlight }
> 실수 데이터타입의 선언 float? double?

> **실수는 double타입이 기준이 된다** (정수는 int형이 기준)
>
> 그 외에는 입출력하는 데이터의 저장가능 범위를 숙지하고 그에 맞는 데이터타입을 사용한다
>
> 이전 수업에서 데이터타입 개념을 정리한 링크 버튼을 첨부한다

[Link button](https://jgoo99.github.io/docs/programing.md/java.md/data_type/#ii-%EB%B3%80%EC%88%98-%EC%84%A4%EC%A0%95-%EB%B0%A9%EB%B2%95){: .btn .btn-purple }