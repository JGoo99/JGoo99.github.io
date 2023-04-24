---
layout: default
title: 입출력과 사칙연산
parent: Algorithm
grand_parent: Language
nav_order: 2
has_children: true
---

_2023.04.20~2023.04.21_

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

# 입출력과 사칙연산

---

## #문제_2557

> Hello World!를 출력하시오.

---

### #입력

> 없음

### #출력

> Hello World!를 출력하시오

### #알고리즘 분류

> 구현

---

### #풀이

```java
public class Main {
  public static void main(String[] args) {
    System.out.println("Hello World!");
  }
}
```

---

### #유의할 점

{: .highlight }
> 출력해야할 문장을 꼼꼼히 확인하자

> 느낌표 하나, 온점 하나도 정확히 파악하자

<br/><br/>

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

<br/><br/>

## #문제_1001

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

{: .highlight }
> Scanner 입력의 데이터 타입을 확실히하자

> **정수를 받을 경우**
>
> int A = i.nextInt();

> **문자열을 받을 경우**
>
> String A = i.next();

<br/><br/>

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

<br/><br/>

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

<br/><br/>

## #문제_10869

> 두 자연수 A와 B가 주어진다. 이때, A+B, A-B, A*B, A/B(몫), A%B(나머지)를 순서대로 출력하는 프로그램을 작성하시오. 

---

### #입력

> 7, 3

### #출력

> 10
>
> 4
>
> 21
>
> 2
>
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
	  
    System.out.println(A+B);
    System.out.println(A-B);
    System.out.println(A*B);
    System.out.println(A/B);
    System.out.println(A%B);
  }
}
```

---

### #유의할 점

{: .highlight }
> print() 와 println()의 차이

> **print()**
>
> 줄바꿈을 하지 않는 순수 프린트 명령어

> **println()**
>
> print + line 으로 자동 줄바꿈을 해주는 명령어

<br/><br/>

## #문제_10926

> **준하가 가입하려고 하는 사이트에 이미 존재하는 아이디가 주어졌을 때, 놀람을 표현하는 프로그램을 작성하시오.**
> 
> 준하는 사이트에 회원가입을 하다가 joonas라는 아이디가 이미 존재하는 것을 보고 놀랐다. 
>
> 준하는 놀람을 ??!로 표현한다. 

---

### #입력

> joonas

### #출력

> joonas??!

### #알고리즘 분류

> 구현

---

### #풀이

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
	  
    Scanner i = new Scanner(System.in);
    System.out.println(i.next() + "??!");
  }
}
```

---

### #오답노트

<br/>

- 나의 제출 답안

> 이미 존재하는 아이디를 배열로 저장한 후 입력받은 아이디와 같은 아이디가 있을 떄 
>
> 해당 아이디와 ??!를 출력하는 로직으로 풀었다

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
	  
    String[] member = {"goo", "jin", "joonas"};
		
    Scanner i = new Scanner(System.in);
    String ID = i.next();
	  
    for (String e : member) {
      if (ID.equals(e))
        System.out.println(ID + "??!");
    }
  }
}
```

<br/>

- **WHY** : 왜 틀렸는가

> "이미 존재하는 아이디" 라는 워딩에서 배열로 저장해야겠다고 생각했다

<br/>

- **HOW** : 어떻게 풀어야하는가

> 해당 문제는 간단한 입출력을 요구하는 문제임을 감안했을 때
>
> String으로 Scanner를 사용하는 방법 정도만 숙지하면 되는 문제였다


---

### #유의할 점

{: .highlight }
> 코드의 최적화

> Scanner로 입력받은 값을 문자열에 따로 저장한 후 출력하는 방법도 있지만
>
> 문자변수가 필요하지 않다면, 저장하지 않고 바로 출력할 수도 있다 
>
> _아래 참고_

<br/>

_문자열 저장 후 출력_

```java
Scanner i = new Scanner(System.in);
String ID = i.next();
System.out.println(ID + "??!");
```

_바로 출력_

```java
Scanner i = new Scanner(System.in);
System.out.println(i.next() + "??!");
```

<br/><br/>

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

> 예수의 탄생연도를 기준으로 삼은 것 (불기연도-543)

- 불기

> 부처의 열반연도를 기준으로 삼은 것 (서기연도+543)

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

<br/><br/>

## #문제_10430

> **세 수 A, B, C가 주어졌을 때, 아래의 네 가지 값을 구하는 프로그램을 작성하시오.**
>
> (A+B)%C는 ((A%C) + (B%C))%C 와 같을까?
>
> (A×B)%C는 ((A%C) × (B%C))%C 와 같을까?

---

### #입력

> 5, 8, 4

### #출력

> 1
>
> 1
>
> 0
>
> 0

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
    int C = i.nextInt();
	  
    System.out.println( (A+B) % C );
    System.out.println( ( (A%C) + (B%C) ) % C );
    System.out.println( (A*B) % C );
    System.out.println( ( (A%C) * (B%C) ) % C );
	  
    i.close();
  }
}
```

---

### #유의할 점

{: .highlight }
> 스캐너 닫기 scanner.close(); 

> Scanner에 **System.in** 해주었다면 사용종료 후 꼭 닫아야한다
>
> 안 닫을 경우 아래와 같은 경고문이 뜬다
>
> Resource leak:'scanner' is never closed
> 
> **닫는 방법 : i.close();** 

<br/><br/>

## #문제_2588

> (1)과 (2)위치에 들어갈 세 자리 자연수가 주어질 때 (3), (4), (5), (6)위치에 들어갈 값을 구하는 프로그램을 작성하시오.

![joon1_10](https://user-images.githubusercontent.com/126454114/233568872-fdc8404c-0114-47c4-9bfa-5f806c18bd6e.jpg)


---

### #입력

> 472
>
> 385

### #출력

> 2360
>
> 3776
>
> 1416
>
> 181720


### #알고리즘 분류

> 수학, 사칙연산

---

### #풀이

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
	  
    Scanner i = new Scanner(System.in);
    int A = i.nextInt();
    int B = i.nextInt();
	  
    int a = A * (B%10);         //472 * 5
    int b = A * (B%100 - B%10); //472 * (85 - 5)
    int c = A * (B - B%100);    //472 * (385 - 85)
	 
    System.out.println( a );
    System.out.println( b/10 );
    //전체값을 구할 땐 그대로 사용해도 되지만, 출력값에서는 일의자리수 생략
    System.out.println( c/100 );
    //위와 같은 맥락
    System.out.println( a+b+c );
  }
}
```

---

### #유의할 점

{: .highlight }
> 유지보수가 좋은 코드에 대한 고민

> 솔직히 입력받는 숫자가 주어진 문제이기 때문에 10으로 나누는 번거로움보다
>
> 그냥 -5, -85를 하면 아주 쉽게 원하는 출력값을 낼 수 있다
>
> 하지만 입력값이 바뀐다면 내가 작성한 코드는 쓸모없는 함수가 된다
>
> 따라서 입력값이 바뀌었을 때도 사용할 수 있는 코드에 대해 고민을 했다

<br/><br/>

## #문제_11382

> 꼬마 정민이는 이제 A + B 정도는 쉽게 계산할 수 있다. 이제 A + B + C를 계산할 차례이다!
>
> A, B, C ( 1 ≤ A, B, C ≤ 10^12 )

---

### #입력

> 77, 77, 7777

### #출력

> 7931

### #알고리즘 분류

> 수학, 구현, 사칙연산

---

### #풀이

```java
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
	  
    Scanner sc = new Scanner(System.in);
		
    long A = sc.nextLong();
    long B = sc.nextLong();
    long C = sc.nextLong();
    //int형보다 더 큰 값이 입력될 수도 있음
		
    System.out.println( A+B+C );
		
    sc.close();
  }
}
```

---

### #오답노트

<br/>

- 나의 제출 답안

```java
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
	  
    Scanner sc = new Scanner(System.in);
		
    int A = sc.nextInt();
    int B = sc.nextInt();
    int C = sc.nextInt();
		
    System.out.println( A+B+C );
		
    sc.close();
  }
}
```

<br/>

- **WHY** : 왜 틀렸는가

> 입력받는 데이터타입을 저장 가능 범위에 못 미치는 int형으로 선언했다
>
> 이클립스에서는 잘 돌아갔으나, 제출 조건에 어긋나므로 런타임 에러가 떴다
>
> **Error : 런타입에러(InputMisMatch)**

<br/>

- **HOW** : 어떻게 풀어야하는가

> 제시된 문제에는 주어지는 데이터 범위가 10^12까지 이므로
>
> long타입으로 선언해야한다

```java
int A = sc.nextInt();   //런타임 에러 (input mismatch)
long A = sc.nextLong(); //에러 해결
```

---

### #유의할 점

{: .highlight }
> 정수형 데이터타입의 구분

> 정수 데이터 타입 : byte, short, int, long
>
> 차이점 : 저장 가능 범위, 메모리 크기

> 위에서 10^12까지의 범위가 수용가능해야 하므로 int형이 아닌 long타입을 사용해야한다
>
> _이전 수업에서 배웠던 데이터타입 링크를 아래에 첨부한다_


[Link button](https://jgoo99.github.io/docs/programing.md/java.md/data_type/#ii-%EB%B3%80%EC%88%98-%EC%84%A4%EC%A0%95-%EB%B0%A9%EB%B2%95){: .btn .btn-green }

<br/><br/>

## #문제_10171

> 아래와 같이 고양이를 출력하시오.

---

### #입력

> 없음

### #출력

![joon1_12](https://user-images.githubusercontent.com/126454114/233665812-b46d9ed6-d454-4330-b3fe-4fc7582d2e3a.jpg)

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
> 역슬래시(\), 따옴표(',")
>
> _이를 **이스케이프 시퀀스**라 하며 이에 관하여 정리한 링크를 아래에 첨부한다_

[Link button](https://jgoo99.github.io/docs/programing.md/java.md/escape/){: .btn .btn-outline }

<br/><br/>

## #문제_10172

> 아래와 같이 개를 출력하시오.

---

### #입력

> 없음

### #출력

![joon1_13](https://user-images.githubusercontent.com/126454114/233666156-c3f483de-71e0-4e87-8451-8c809b3d2319.jpg)

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
