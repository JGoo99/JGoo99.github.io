---
layout: default
title: 반복문
parent: Algorithm
grand_parent: Language
nav_order: 4
---

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

# 반복문
{: .no_toc }

---

## #문제_2739

> N을 입력받은 뒤, 구구단 N단을 출력하는 프로그램을 작성하시오. 출력 형식에 맞춰서 출력하면 된다.

---

### #입력
{: .no_toc }

> 2

### #출력
{: .no_toc }

> 2 * 1 = 2
>
> 2 * 2 = 4
>
> 2 * 3 = 6
> 
> 2 * 4 = 8
>
> 2 * 5 = 10
>
> 2 * 6 = 12
> 
> 2 * 7 = 14
>
> 2 * 8 = 16
>
> 2 * 9 = 18


### #알고리즘 분류
{: .no_toc }

> 수학, 구현

---

### #풀이
{: .no_toc }

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    byte N = sc.nextByte();

    for (int i = 1; i<10; i++) {
      System.out.println( N + " * " + i + " = " + (N*i) );
    }
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 변수의 중복

> Scanner의 객체명을 i로 지정했을 경우 for에서 자주쓰이는 변수 i와 겹친다
>
> 따라서 간단한 코드 작성 시에도 변수명을 미리 계획하고 생각하는 습관을 기르자

<br/><br/><br/>

---

## #문제_10950

> 두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.

---

### #입력
{: .no_toc }

> 5
>
> 1 1
>
> 2 3
>
> 3 4
>
> 9 8
>
> 5 2

### #출력
{: .no_toc }

> 2
>
> 5
>
> 7
>
> 17
>
> 7

### #알고리즘 분류
{: .no_toc }

> 수학, 구현, 사칙연산

---

### #풀이
{: .no_toc }

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    byte A, B, inCase;

    Scanner sc = new Scanner(System.in);
    inCase = sc.nextByte();

    for (byte i = 0; i < inCase; i++) {
      A = sc.nextByte();
      B = sc.nextByte();
      System.out.println(A+B);
    }
  }
}
```

---

### #오답노트

<br/>

- 나의 제출 답안

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    byte A, B, inCase;

    Scanner sc = new Scanner(System.in);
    inCase = (byte) (sc.nextByte()+1);

    for (byte i = 0; i < inCase; i++) {
      A = sc.nextByte();
      B = sc.nextByte();
      System.out.println(A+B);
    }
  }
}
```

<br/>

- **WHY** : 왜 틀렸는가

> 반복 횟수가 1만큼 더 많기 때문에 런타임 에러가 떴다

<br/>

- **HOW** : 어떻게 풀어야하는가

> inCase 변수를 사용하여 1만큼 더 더해주었는데 i는 0부터 시작하기 때문에 더해줄 필요가 없다
>
> 따라서 더하거나 빼는 과정 없이 sc.nextByte()만 받아도 된다

```java
byte inCase = sc.nextByte();
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 사칙연산을 한 변수

> byte A = 3+inCase;
>
> 위의 경우 에러가 발생한다 따라서 아래처럼 선언해야 한다
>
> byte A = (byte) (3+inCase);

<br/><br/><br/>

---

## #문제_8393

> n이 주어졌을 때, 1부터 n까지 합을 구하는 프로그램을 작성하시오.

---

### #입력
{: .no_toc }

> 3

### #출력
{: .no_toc }

> 6

### #알고리즘 분류
{: .no_toc }

> 수학, 구현

---

### #풀이
{: .no_toc }

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    int sum=0, n;
    Scanner sc = new Scanner(System.in);
    n = sc.nextInt();

    for (int i=1; i < (n+1); i++) {
      sum = (int) (sum + i);
    }
    System.out.println(sum);
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> sum += i;

> sum = (int) (sum+i);
>
> 위의 문장은 아래 문장과 정확히 동일하다
>
> sum += i;

<br/><br/><br/>

---

## #문제_25304

> **구매한 물건의 가격과 개수로 계산한 총 금액이 영수증에 적힌 총 금액과 일치하는지 검사해보자.**
>
> 첫째 줄에는 영수증에 적힌 총 금액 X가 주어진다.
>
> 둘째 줄에는 영수증에 적힌 구매한 물건의 종류의 수 N이 주어진다.
>
> 이후 N개의 줄에는 각 물건의 가격 a와 개수 b가 공백을 사이에 두고 주어진다.
>
> 구매한 물건의 가격과 개수로 계산한 총 금액이 영수증에 적힌 총 금액과 일치하면 Yes를 출력한다. 일치하지 않는다면 No를 출력한다.

---

### #입력
{: .no_toc }

> 260000
>
> 4
>
> 20000 5
>
> 30000 2
>
> 10000 6
>
> 5000 8

### #출력
{: .no_toc }

> Yes

### #알고리즘 분류
{: .no_toc }

> 수학, 구현, 사칙연산

---

### #풀이
{: .no_toc }

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    int sum = 0;

    Scanner sc = new Scanner(System.in);
    int X = sc.nextInt();
    byte N = sc.nextByte();

    for (int i = 0; i < N; i++) {
      int a = sc.nextInt();
      int b = sc.nextByte();
      sum += a * b;
    }

    if (sum == X) {
      System.out.println("Yes");
    } else {
      System.out.println("No");
    }
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 사칙연산의 정확성

> 물건 값과 개수의 곱을 구해야 하는데 더하기를 하는 등의 실수를 주의하자

<br/><br/><br/>

---

## #문제_11021

> **두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.**

> (0 < A, B < 10)

---

### #입력
{: .no_toc }

> 5
>
> 1 1
>
> 2 3
>
> 3 4
>
> 9 8
>
> 5 2

### #출력
{: .no_toc }

> Case #1: 2
>
> Case #2: 5
>
> Case #3: 7
>
> Case #4: 17
>
> Case #5: 7

### #알고리즘 분류
{: .no_toc }

> 수학, 구현, 사칙연산

---

### #풀이
{: .no_toc }

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    int Case = sc.nextInt();

    for (int i = 0; i < Case; i++) {
      byte x = (byte) (i+1);
      int A = sc.nextInt();
      int B = sc.nextInt();
      System.out.println("Case #" +x + ": "+(A+B));
    }
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 고정 입력값을 반복문 안에 넣지 않기

> Case 숫자를 입력받는 문장을 반복문 안에 넣게되면
>
> 계속해서 Case가 초기화 되면서 로직이 꼬이게 된다

<br/><br/><br/>

---

## #문제_25314

> **N바이트 정수까지 저장할 수 있다고 생각하는 정수 자료형의 이름을 출력하여라.**

> ( 4 =< N =< 1,000 ) N은 4의 배수

---

### #입력
{: .no_toc }

> 20

### #출력
{: .no_toc }

> long long long long long int

### #알고리즘 분류
{: .no_toc }

> 구현

---

### #풀이
{: .no_toc }

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    short N = sc.nextShort();

    for (int i = 0; i < (N/4); i++) {
      System.out.print( "long " );
    }
    System.out.print("int");
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 띄어쓰기 중요성

> 일일이 출력하여 확인하는 것도 좋지만, 코드가 더 복잡해질 수 있으므로
>
> 내가 의도한대로 출력될 수 있도록 계획적으로 여백을 넣자

<br/><br/><br/>

---

## #문제_15552

> **각 테스트케이스마다 A+B를 한 줄에 하나씩 순서대로 출력한다. 단, 제한시간은 1초이다.**

> ( 1 =< A, B =< 1,000 )
>
> T < 1,000,000

---

### #입력
{: .no_toc }

> 5
>
> 1 1
>
> 12 34
>
> 5 500
>
> 40 60
>
> 1000 1000

### #출력
{: .no_toc }

> 2
>
> 46
>
> 505
>
> 100
>
> 2000

### #알고리즘 분류
{: .no_toc }

> 수학, 구현, 사칙연산

---

### #풀이
{: .no_toc }

```java
import java.io.*;

class Main {
  public static void main(String[] args) throws IOException {
    int T; //케이스 개수
    short A, B; //입력받는 두 정수

    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));

    T = Integer.parseInt(br.readLine());

    for (int i = 0; i < T; i++) {
      String[] strs = br.readLine().split(" ");
      A = Short.parseShort(strs[0]);
      B = Short.parseShort(strs[1]);
      bw.write(String.valueOf(A+B));
      bw.newLine();
    }
    bw.flush();
    bw.close();
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> BufferedReader

> 키보드로 입력하는 순간 저장하는 방식으로, 입력시간을 최소화 시켜준다
>
> 단, 아래 사항을 지켜주어야 한다
>
> 1. 예외처리 ( throws IOException / try and catch )
>
> 2. 클래스임포트 ( import java.io.*; )
>
> 3. 데이터 가공 ( String[] strs = br.readLine().split(" ") )

<br/>

{: .highlight }
> BufferedWriter

> 버퍼의 출력방식으로 출력시간을 최소화 시켜준다
>
> 단, 아래 사항을 지켜주어야 한다
>
> 1. 개행처리 ( bw.newLine() )
>
> 2. 뒤처리 ( bw.flush(), bw.close() )


<br/><br/><br/>

---

## #문제_11022

> **각 테스트 케이스마다 "Case #x: A + B = C" 형식으로 출력한다. x는 테스트 케이스 번호이고 1부터 시작하며, C는 A+B이다.**

> ( 0 =< A, B =< 10 )
>
> T < 1,000,000

---

### #입력
{: .no_toc }

> 5
>
> 1 1
>
> 2 3
>
> 3 4
>
> 9 8
>
> 5 2

### #출력
{: .no_toc }

> Case #1: 1 + 1 = 2
>
> Case #2: 2 + 3 = 5
>
> Case #3: 3 + 4 = 7
>
> Case #4: 9 + 8 = 17
>
> Case #5: 5 + 2 = 7

### #알고리즘 분류
{: .no_toc }

> 수학, 구현, 사칙연산

---

### #풀이
{: .no_toc }

```java
import java.io.*;

class Main {
  public static void main(String[] args) throws IOException {
    int T; //케이스 개수
    byte A, B; //입력받은 두 정수

    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    T = Integer.parseInt(br.readLine());
    BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));

    for (int i = 0; i < T; i++) {
      String[] strs = br.readLine().split(" ");
      A = Byte.parseByte(strs[0]);
      B = Byte.parseByte(strs[1]);
			
      bw.write("Case #" + (i+1) + ": ");
      bw.write(A + " + " + B + " = ");
      bw.write(String.valueOf(A+B));
      bw.newLine();
    }
    bw.flush();
    bw.close();
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 연산자의 우선순위

> 연산자끼리도 우선 계산되는 순위가 있으므로 정확한 출력을 위해 알고있어야 한다
>
> 아래 정리해놓은 표 링크를 첨부한다

[Link button](https://jgoo99.github.io/docs/language.md/java1.md/operator/#5-%EA%B8%B0%EB%B3%B8%EC%97%B0%EC%82%B0%EC%9E%90%EC%9D%98-%EC%9A%B0%EC%84%A0%EC%88%9C%EC%9C%84){: .btn .btn-outline }

<br/><br/><br/>

---

## #문제_2438

> **첫째 줄에는 별 1개, 둘째 줄에는 별 2개, N번째 줄에는 별 N개를 찍는 문제**

> (1 ≤ N ≤ 100)

---

### #입력
{: .no_toc }

> 5

### #출력
{: .no_toc }

![joon3_2](https://user-images.githubusercontent.com/126454114/236755012-a499e505-c405-45d3-b453-972af86edfa2.jpg)

### #알고리즘 분류
{: .no_toc }

> 구현

---

### #풀이
{: .no_toc }

- scanner 사용

```java
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
    byte N; //테스트 개수

    Scanner sc = new Scanner(System.in);
    N = sc.nextByte();

    for (int i = 0; i < N ; i++) {
      for (int j = 0; j < (i+1); j++) {
        System.out.print("*");
      }
      if (i == N-1) {
        sc.close();
      } else System.out.print('\n');
    }
  }
}
```

<br/>

- buffer 사용

```java
import java.io.*;

class Main {
  public static void main(String[] args) throws IOException {
    byte N; //케이스 개수

    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
    N = Byte.parseByte(br.readLine());
    br.close();

    for (int i = 0; i < N; i++) {
      for (int j = 0; j < i+1; j++) {
        bw.write('*');
      }
      if (i == N-1) {
        bw.flush();
        bw.close();
      } else bw.newLine();
    }
  }
}
```

> buffer를 사용할 경우 메모리와 시간을 모두 절약할 수 있다 (위: buffer, 아래: scanner)

![joon3_1](https://user-images.githubusercontent.com/126454114/236752307-ab0b23bf-b591-4cd4-81e0-412eff18839f.jpg)

---

### #유의할 점
{: .no_toc }

{: .highlight }
> **System.out.print()** vs **System.out.printf()**

> **System.out.print()**는 단순한 콘솔 출력에 사용하고
>
> **System.out.printf()**는 %d와 %n등을 활용하여 좀 더 복잡한 출력에 사용된다
>
> 아래 예시를 통해 확인하자

```java
String name = "Goo";
int age = 24;

System.out.println("hello");
//출력 후 자동 개행
System.out.print("hello im Goo");
//간단한 출력 (개행x)
System.out.println();
System.out.printf("hello im %s, and im %d", name, age);
```

```java
hello
hello im Goo
hello im Goo, and im 24
```

<br/><br/><br/>

---

## #문제_2439

> **첫째 줄에는 별 1개, 둘째 줄에는 별 2개, N번째 줄에는 별 N개를 찍는 문제(단, 오른쪽 정렬)**

> (1 ≤ N ≤ 100)

---

### #입력
{: .no_toc }

> 5

### #출력
{: .no_toc }

![joon3_3](https://github.com/JGoo99/java-project/assets/126454114/4a507c0d-2254-4470-a93e-ae1d95f63c0b)

### #알고리즘 분류
{: .no_toc }

> 구현

---

### #풀이
{: .no_toc }

```java
import java.io.*;

class Main {
  public static void main(String[] args) throws IOException {
    int N; //테스트개수

    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    N = Integer.parseInt(br.readLine());
    br.close();

    BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));

    for (int i = 0; i < N; i++) {
      for (int j = 1; j < N-i; j++) {
        bw.write(" ");
      }
      for (int l = 0; l < i+1; l++) {
        bw.write('*');
      }
      bw.flush();
      if (i == N-1) {
        bw.flush();
        bw.close();
      } else {
        bw.newLine();
      }
    }
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> 반복문 변수 초기화

> 반복문 조건 괄호 안에 초기화할 때 머리속에서 시물레이션을 돌리면서
>
> 몇번의 반복이 필요할지, 어떤 수로 초기화 할지 구상하고 입력하도록 한다
>
> 감이 안 잡히면 실제로 돌려보면서 어떤 오류가 발생하는지 확인하면 좋다

<br/><br/><br/>

---

## #문제_10952

> **두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.**

> **입력의 마지막에 0 두 개가 들어오면 종료**

---

### #입력
{: .no_toc }

> 1 1
>
> 2 3
>
> 3 4
>
> 9 8
>
> 5 2
>
> 0 0

### #출력
{: .no_toc }

> 2
>
> 5
>
> 7
>
> 17
>
> 7

### #알고리즘 분류
{: .no_toc }

> 수학, 구현, 사칙연산

---

### #풀이
{: .no_toc }

```java
import java.io.*;

class Main {
  public static void main(String[] args) throws IOException {
    int A, B; //입력받는 두 정수

    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));

    while (true) {
      String[] strs = br.readLine().split(" ");
      A = Integer.parseInt(strs[0]);
      B = Integer.parseInt(strs[1]);

      if (A + B == 0) {
        bw.flush();
        bw.close();
        break;
      } else {
        bw.write(String.valueOf(A+B));
        bw.newLine();
      }
    }
  }
}
```

---

### #유의할 점
{: .no_toc }

{: .highlight }
> break;

> while (true) {} 반복문을 사용할 때는 꼭 break를 이용하여 종료하도록 한다

<br/><br/><br/>

---

## #문제_10951

> **두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.**

---

### #입력
{: .no_toc }

> 1 1
>
> 2 3
>
> 3 4
>
> 9 8
>
> 5 2

### #출력
{: .no_toc }

> 2
>
> 5
>
> 7
>
> 17
>
> 7

### #알고리즘 분류
{: .no_toc }

> 수학, 구현, 사칙연산

---

### #풀이
{: .no_toc }

- Scanner 사용

```java
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
    int A, B; //입력받는 두 정수

    Scanner sc = new Scanner(System.in);

    while (sc.hasNextInt()) {
    //입력값이 정수=true
    //정수가 아닐 경우 false를 반환하며 종료
      A = sc.nextInt();
      B = sc.nextInt();
      System.out.println(A+B);
    }
    sc.close();
  }
}
```

- Buffer 사용

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.StringTokenizer;

class Main {
  public static void main(String[] args) throws IOException {
    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    StringBuilder sb = new StringBuilder();
    StringTokenizer st;
    String str;

    while ( (str = br.readLine()) != null) {
      st = new StringTokenizer(str, " ");
      int A = Integer.parseInt(st.nextToken());
      int B = Integer.parseInt(st.nextToken());
      sb.append(A+B).append('\n');
    }
    System.out.print(sb);
  }
}
```

[Link button](https://st-lab.tistory.com/40){: .btn .btn-outline }
---

### #유의할 점
{: .no_toc }

{: .highlight }
> EOF (End Of File)

> **입력에서 더이상의 읽을 수 있는 데이터가 존재하지 않을 때 반복문을 종료하라는 것**
>
> 맥에서는 cmd+d를 입력하면 null값을 반환한다

<br/>

{: .highlight }
> StringTokenizer

> .split(" ")과 비슷하지만 성능측면에서 더 좋다
>
> str 문자열에서 " "을 기준으로 저장하는 형식이다

```java
StringTokenizer st = new StringTokenizer(str, " ");
```

<br/><br/><br/>