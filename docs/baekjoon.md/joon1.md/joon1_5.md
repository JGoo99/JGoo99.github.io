---
layout: default
title: A/B
parent: 입출력과 사칙연산
grand_parent: 백준 문제풀이
nav_order: 6
---

## 1. 문제

> 두 정수 A와 B를 입력받은 다음, A/B를 출력하는 프로그램을 작성하시오.

---

### 1. 입력

> 1 3

### 2. 출력

> 0.33333333333333333333333333333333
>
> _오차 허용_

### 3. 알고리즘 분류

> 수학, 구현, 사칙연산

---

# 풀이

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

# 유의할 점

{: .highlight }
> 실수 데이터타입의 선언 float? double?

> 정수는 int형이 기준, 실수는 double이 기준이 된다
>
> _+)두 타입 모두 정밀도에서 근본적인 문제가 존재한다_
>
> 이전 수업에서 연산자 개념을 정리한 링크 버튼을 첨부한다

[Link button](https://jgoo99.github.io/docs/programing.md/java.md/data_type/){: .btn .btn-purple }