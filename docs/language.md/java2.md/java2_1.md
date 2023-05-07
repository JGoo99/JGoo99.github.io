---
layout: default
title: 변수
parent: Java 심화
grand_parent: Language
nav_order: 2
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

# I. 변수
{: .no_toc }

---

## 변수와 상수

### i. 변수란?
{: .no_toc }

> **단 하나의 값을 저장할 수 있는 메모리 공간**
>
> 이 수는 변경할 수 있기 때문에 변수라고 명명

<br/><br/>

### ii. 변수의 선언과 초기화
{: .no_toc }

- **변수의 선언**

> 변수를 사용하기 위해 변수 타입과 이름을 정하는 것

```java
int age;
//변수타입 변수이름
```

<br/>

- **변수의 초기화**

> **변수를 사용하기 전에 처음으로 값을 저장하는 것**
>
> 오른쪽의 값을 왼쪽에 대입한다

```java
int age = 24, year = 2023;
```

<br/>

{: .new-title }
> 두 변수의 값 교환하기
>
> x와 y에 각각 초기화된 값을 바꿔보자

```java
class Main {
  public static void main(String[] args) {
    int x=5, y=10;
    int temp = 0;

    System.out.println("x:" + x + " y:" + y);

    temp = x; 
    x = y;
    y = temp;

    System.out.println("x:" + x + " y:" + y);
  }
}
```

```java
x:5 y:10
x:10 y:5
```

> 단순히 x=y, y=x로 초기화 하는 것이 아니라
>
> 임시저장소 temp를 선언하여 두 변수 x,y의 값을 교환해야 한다

<br/><br/>

### iii. 변수의 명명규칙
{: .no_toc }

- **대소문자**가 구분되며 **길이에 제한이 없다**

- 예약어를 사용해서는 안 된다

- **숫자로 시작**해서는 **안 된다**

- 특수문자는 **_와 $**만 허용된다

- **클래스** 이름의 첫글자는 항상 **대문자**로 한다

- 여러 단어로 이루어진 이름은 단어의 첫 글자를 대문자로 한다

- **상수**의 이름은 **모두 대문자**로 한다 (여러 단어로 이루어진 경우 _로 구분한다)


---

## 변수의 타입

### i. 기본형과 참조형
{: .no_toc }

- **자료형**

> data의 type에 따라 값이 저장될 공간의 크기와 저장형식을 정의한 것으로
>
> 자료형은 크게 기본형과 참조형으로 나뉜다

<br/>

- **참조형**

> 어떤 값이 저장된 주소를 값으로 저장하는 자료형이다 

```java
Data today = new Data();
//클래스이름 변수이름 = 생성된 객체의 주소
```

<br/>

- **기본형**

> 실제 값을 저장하는 자료형으로 문자형, 정수형, 실수형, 논리형 등이 있다

|분류     |타입                       |
|:-------|:-------------------------|
|논리형    |boolean                   |
|문자형    |char                      |
|정수형    |byte, short, **int**, long|
|실수형    |float, **double**         |

> 기본형의 종류와 크기는 아래와 같다

|종류/크기  |  1byte  |  2byte  |  4byte  |  8byte  |
|:-------:|:-------:|:-------:|:-------:|:-------:|
|논리형     |boolean  |         |         |         |
|문자형     |         |char     |         |         |
|정수형     |byte     |short    |**int**  |long     |
|실수형     |         |         |float    |**double**|

<br/><br/>

### ii. 상수와 리터럴
{: .no_toc }

- **상수**

> 값을 저장할 수 있는 공간 (단, 값을 변경할 수 없으며, **선언과 동시에 초기화해야 한다**)

```java
final int MAX_VALUE = 100; 
```

<br/>

- **숫자 리터럴**

> 숫자 그 자체의 값으로, 선언 시 접미사가 필요한 경우가 있다
>
> 접미사가 필요한 데이터 타입: **long, float** (int와 double로 자동 설정됨)

{: .warning-title }
> Error
>
> 리터럴 값의 범위 > 변수의 타입

<br/>

- **문자/문자열 리터럴**

> 문자 리터럴: ''로 감싼 한 문자 이상의 데이터
>
> 문자열 리터럴: ""로 감싼 빈 문자열 이상의 데이터

{: .important-title }
> 🐷
>
> 기본/참조형 구별 없이 **어떤 타입의 변수도 문자열과 덧셈하면 결과는 문자열이 된다**
>
> 단, 덧셈연산은 왼쪽부터 수행하므로 그 결과값이 달라질 수 있다

```java
System.out.println( 7 + 7 + "" );
System.out.println( "" + 7 + 7 );
```

```java
14
77
```

<br/><br/>

### iii. 형식화된 출력
{: .no_toc }

> 지금까지는 println()을 사용하였다 이번에는 형식화하여 출력하는 printf()를 알아보자

<br/>

- **printf()**

> 기능: 지시자를 통하여 변수의 값을 여러 가지 형식으로 변환하여 출력한다
>
> 특징: println()과 다르게 줄바꿈을 하지 않는다

<br/>

- **지시자**

> 값을 어떻게 출력할 것인지 정하는 역할

| 지시자 | 설명 |
|:----:|:----------:|
| %b      | boolean  |
| %d      | 10진 정수  |
| %o      | 8진 정수   |
| %x, %X  | 16진 정수  |
| %f      | 부동 소수점 |
| %e,%E   | 지수 표현식 |
| %c      | 문자      |
| %s      | 문자열     |

```java
System.out.printf("age: %d year: %d, 24, 2023)
```

<br/><br/>

### vi. 화면에서 입력받기
{: .no_toc }

> Scanner를 활용한 콘솔 입력받기

```java
String input = sc.nextLine(); 
int num = Integer.parseInt(input); // 입력받은 내용을 input타입의 값으로 변환
```

> Scanner는 nextInt()나 nextByte() 등 데이터 타입별로 입력받을 수 있다
>
> 단 연속적으로 입력받을 경우 데이터 타입을 지정하는 것은 복잡할 수 있다
>
> 따라서 아래처럼 nextLine()을 이용하여 String으로 입력받은 후 형변환처리를 하자

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);

    System.out.println("두 자리 정수를 입력하시오");
    String input = sc.nextLine();
    int num = Integer.parseInt(input);

    System.out.println("입력내용: "+input);
    System.out.printf("num= %d%n", num);
  }
}
```

```java
두 자리 정수를 입력하시오
22
입력내용: 22
num= 22
```

---

## 진법

### i. 10진법과 2진법
{: .no_toc }

> 지금까지 리터럴을 저장할 때 10진법을 사용한 것 같았지만
>
> 사실 10진 숫자들은 모두 컴퓨터가 이해할 수 있는 2진법으로 해석되어 저장되어 왔다
>
> 아래 표를 통해 2진법을 살펴보자

| 2진법 | 10진법 |
|:----:|:-----:|
| 0 | 0 |
| 1 | 1 |
| 10 | 2 |
| 11 | 3 |
| 100 | 4 |
| 101 | 5 |
| 110 | 6 | 
| 111 | 7 |
| 1000 | 8 | 
| 1001 | 9 |
| 1010 | 10 |

<br/><br/>

### ii. 비트와 바이트
{: .no_toc }

> **비트**: bit, 한 자리의 2진수
>
> **바이트**: byte, 여덟 자리의 2진수 (=8bit)
>
> **워드**: word, CPU가 한 번에 처리할 수 있는 데이터의 크기

<br/><br/>

### iii. 8진법과 16진법
{: .no_toc }

> 2진법은 두 개의 숫자로만 표현하기 때문에 자릿수가 너무 많아진다는 단점이 있다
>
> 이 단점을 보안하기 위해 나온 것이 8진법과 16진법이다

| 2진법 | 8진법 | 10진법 | 16진법 | 
|:----:|:----:|:----:|:----:|
| 0 | 0 | 0 | 0 |
| 1 | 1 | 1 | 1 |
| **10** | 2 | 2 | 2 | 
| 11 | 3 | 3 | 3 |
| 100 | 4 | 4 | 4 |
| 101 | 5 | 5 | 5 |
| 110 | 6 | 6 | 6 |   
| 111 | 7 | 7 | 7 |
| 1000 | **10** | 8 | 8 |
| 1001 | 11 | 9 | 9 |
| 1010 | 12 | **10** | A | 
| 1011 | 13 | 11 | B |
| 1100 | 14 | 12 | C |
| 1101 | 15 | 13 | D |
| 1110 | 16 | 14 | E |
| 1111 | 17 | 15 | F | 
| 10000 | 20 | 16 | **10** |

<br/>

- 2진수의 8/16진수 변환

> **2진수 > 8진수**: 3자리씩 끊어서 그에 해당하는 8진수로 바꾸기
>
> **2진수 > 16진수**: 4자리씩 끊어서 그에 해당하는 16진수로 바꾸기

```java
1010101100

//8진수로 바꾸기
1_010_101_100 //1254

//16진수로 바꾸기
10_1010_1100 //2AC
```

---

## 기본형

### i. 논리형
{: .no_toc }

> Boolean형 변수 하나 뿐으로 **false**와 **true** 중 하나를 저장할 수 있다
>
> 기본값은 false이며, 대문자를 사용하면 에러가 발생한다

```java
boolean power = true;
boolean checked = False; //Error
```

<br/>

### ii. 문자형
{: .no_toc }

> char형 변수 하나 뿐으로 단 하나의 문자만 저장할 수 있다

```java
char ch = 'A';
```

{: .new-title }
> 문자와 유니코드
>
> 위의 A는 문자로 저장되는 것이 아니라 **유니코드 65**로 저장된다
>
> 문자를 숫자로 변환하여 저장하는 것을 **인코딩**
>
> 숫자를 다시 문자로 출력하는 것을 **디코딩**이라고 한다
>
> 실제로 그러한지 문자와 유니코드를 출력해보자

```java
char ch = '가';
System.out.printf("%c = %d(%#X)", ch, (int)ch, (int)ch);
```

```java
가 = 44032(0XAC00)
```

<br/>

- **특수문자 저장하기**

> 특수문자는 백슬레시를 사용하여 저장해야 한다
>
> 아래 예시와 표를 참고하자

```java
char tab = '\t';
//실제로는 두 개의 문자이지만 하나의 문자로 취급되어 자장된다
```

| 특수문자 | 문자 리터럴 |
|:------:|:--------:|
| tab | \t |
| backspace | \b |
| form feed | \f |
| new line | \n |
| carriage return | \r |
| 역슬래쉬 | \\\ |
| 작은 따옴표 | \' |
| 큰 따옴표 | \" |
| 유니코드(16진수 문자) | \u |

```java
System.out.println("tab :" + '\t' + "."); //tab

System.out.println("backspace :" + "." + '\b' + ".");

System.out.println("form feed :" + '\f' + ".");
		//다음페이지로 넘어감
System.out.println("new line :" + '\n' + ".");

System.out.println("carriage return :" + '\r' + ".");
		//맨 왼 쪽으로 이동
System.out.println("역슬래쉬 :" + '\\');

System.out.println("따옴표 :" + '\'' + '\"' );
```

```java
tab :	.
backspace :.
form feed :.
new line :
.
.
역슬래쉬 :\
따옴표 :'"
```

<br/>

### iii. 정수형
{: .no_toc }

> byte, short, int, long 총 네가지로 각 자료형의 저장 수용 범위가 다르다

### vi. 실수형
{: .no_toc }

---

## 형변환

### i. 형변환이란?
{: .no_toc }

### ii. 형변환 방법
{: .no_toc }

### iii. 정수형 간의 형변환
{: .no_toc }

### vi. 실수형 간의 형변환
{: .no_toc }

### v. 정수형과 실수형 간의 형변환
{: .no_toc }

### vi. 자동 형변환
{: .no_toc }