---
layout: default
title: 불기연도와 서기연도
parent: 입출력과 사칙연산
grand_parent: 백준 문제풀이
nav_order: 9
---

# 입출력과 사칙연산

---

## #문제_18108

> **불기 연도가 주어질 때 이를 서기 연도로 바꿔 주는 프로그램을 작성하시오.**
>
> 불교 국가인 태국은 불멸기원(佛滅紀元), 즉 석가모니가 열반한 해를 기준으로 연도를 세는 불기를 사용한다.
>
> 반면, 우리나라는 서기 연도를 사용하고 있다. 

---

### #입력

> 2541

### #출력

> 1998

### #알고리즘 분류

> 수학, 사칙연산

---

### #풀이

- 서기

> 예수의 탄생연도를 기준으로 삼은 것

- 불기

> 부천의 열반연도를 기준으로 삼은 것

<br/>

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
	  
    Scanner i = new Scanner(System.in);
    System.out.println(i.nextInt() - 543);
  }
}
```

---

### #유의할 점

{: .highlight }
> 입력값의 데이터타입

> 자바는 데이터 타입에 민감한 언어이므로
>
> Scanner에 입력되는 데이터타입에 맞추어 정확히 호출해야한다

