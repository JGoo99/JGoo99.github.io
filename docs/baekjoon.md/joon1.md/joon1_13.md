---
layout: default
title: 개
parent: 입출력과 사칙연산
grand_parent: 백준 문제풀이
nav_order: 14
---

# 입출력과 사칙연산

---

## #문제_10172

> 아래와 같이 개를 출력하시오.

---

### #입력

> 없음

### #출력

> |\_/|
>
> |q p|   /}
>
> ( 0 )"""\
>
> |"^"`    |
>
> ||_/=\\__|

### #알고리즘 분류

> 구현

---

### #풀이

```java
class Main {
  public static void main(String[] args) {
	  
    System.out.println("|\\_/|");
    System.out.println("|q p|   /}");
    System.out.println("( 0 )\"\"\"\\");
    System.out.println("|\"^\"`    |");
    System.out.println("||_/=\\\\__|");
  }
}
```

---

### #유의할 점

{: .highlight }
> 비슷한 특수문자의 차이

> 작은 따옴표는 출력을 위해 역슬래시를 사용해야하고
>
> 백틱은 역슬래시 없이 출력 가능하다
>
> 생김새는 비슷하지만 쓰임과 이름이 다르므로 그 차이를 알아두자


