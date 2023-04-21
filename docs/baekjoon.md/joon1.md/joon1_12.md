---
layout: default
title: 고양이
parent: 입출력과 사칙연산
grand_parent: 백준 문제풀이
nav_order: 13
---

# 입출력과 사칙연산

---

## #문제_10171

> 아래와 같이 고양이를 출력하시오.

---

### #입력

> 없음

### #출력

> \    /\
>
> )  ( ')
>
> (  /  )
>
>  \(__)|

### #알고리즘 분류

> 구현

---

### #풀이

```java
class Main {
  public static void main(String[] args) {
	  
    System.out.println("\\    /\\");
    System.out.println(" )  ( \')");
    System.out.println("(  /  )");
    System.out.println(" \\(__)|");
  }
}
```

---

### #유의할 점

{: .highlight }
> 특수문자의 출력 방법

> 그 자체만으로는 출력이 되지 않는 특수문자에는 역슬래시를 붙여야 한다
>
> **\   '   "**
>
> _이를 **이스케이프 시퀀스**라 하며 이에 관하여 정리한 링크를 아래에 첨부한다_

<div class="code-example" markdown="1">
[Link button](https://jgoo99.github.io/docs/programing.md/java.md/escape/){: .btn }

