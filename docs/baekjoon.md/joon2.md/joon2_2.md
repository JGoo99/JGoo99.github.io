---
layout: default
title: 시험 성적
parent: 조건문
grand_parent: 백준 문제풀이
nav_order: 3
---

# 조건문

---

## #문제_9498

> 시험 점수를 입력받아 등급을 출력하는 프로그램을 작성하시오.
>
> 90 ~ 100점 : A
> 
> 80 ~ 89점 : B
>
> 70 ~ 79점 : C
>
> 60 ~ 69점 : D
>
> 59점 이하 : F

---

### #입력

> 100

### #출력

> A


### #알고리즘 분류

> 구현

---

### #풀이

```java
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
	  
    Scanner sc = new Scanner(System.in);
    Short score = sc.nextShort();
		
    if (score >= 90) 
      System.out.println("A");
      else if (score >= 80)
        System.out.println("B");
      else if (score >= 70)
        System.out.println("C");
      else if (score >= 60)
        System.out.println("D");
      else
        System.out.println("F");
		
    sc.close();
  }
}
```

---

### #유의할 점

{: .highlight }
> **논리연산자** vs **else if**

> 이 문제를 보았을 때 아래의 두 가지 풀이가 생각났다

<br/>

1. if문을 각각 작성하여 논리연산자 사용하기

```java
if (score >= 90) 
  System.out.println("A");
if (score >= 80 && score <= 89)
  System.out.println("B");
if (score >= 70 && score <= 79)
  System.out.println("C");
if (score >= 60 && score <= 69)
  System.out.println("D");
if (score <= 59)
  System.out.println("F");
```

<br/>

{:style="counter-reset:none"}
2. else if문을 활용하기

```java
if (score >= 90) 
  System.out.println("A");
 else if(score >= 80)
   System.out.println("B");
 else if (score >= 70)
   System.out.println("C");
 else if (score >= 60)
   System.out.println("D");
 else
   System.out.println("F");
```

<br/>

> 정답은 없지만 **코드의 중복**을 없애고 **가독성**을 높여주며 **유지보수**가 좋은
>
> 2번 **else if문을 활용하기**를 택했다
>
> _참고로 논리연산자를 정리했던 링크를 아래에 첨부한다_


[Link button](https://jgoo99.github.io/docs/programing.md/java.md/operator/#4-%EB%85%BC%EB%A6%AC-%EC%97%B0%EC%82%B0%EC%9E%90){: .btn .btn-outline }