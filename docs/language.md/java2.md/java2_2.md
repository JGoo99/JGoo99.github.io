---
layout: default
title: 연산자
parent: Java 심화
grand_parent: Language
nav_order: 3
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

# II. 연산자
{: .no_toc }

---

## 연산자

### i. 연산자와 피연산자
{: .no_toc }

- **연산자란?**

> 연산을 수행하는 기호
>
> 피연산자로 연산을 수행하고나면 항상 결과값을 반환한다

<br/>

- **피연산자란?**

> 연산자의 작업 대상

```java
x + 3
//연산자: +
//피연산자: x, 3
```

<br/><br/>

### ii. 식과 대입 연산자
{: .no_toc }

- **식이란?**

> 연산자와 피연산자를 조합하여 계산하고자 하는 것을 표현한 것

<br/>

- **대입연산자란?**

> **=**을 사용하여 오른쪽의 값을 왼쪽에 대입하여 저장한다
>
> 식의 결과값 저장을 위해 아래처럼 표현한다 _새미콜론을 이용하여 문장으로 만들어주어야 한다_

```java
y = x * 3 + 5;
```

<br/><br/>

### iii. 연산자의 종류
{: .no_toc }

- **기능별 분류**

> 산술 : 사칙연산, 나머지연산
>
> 비교 : 크고 작음과 같고 다름을 비교
>
> 논리 : 그리고, 또는 등으로 조건을 연결
>
> 대입 : 우변읙 값을 좌변에 저장
>
> 기타 : 형변환연산자, 삼항연산자, instanceof연산자

<br/>

- **피연산자 개수별 분류**

> 단항연산자 : 피연산자가 1개
>
> 이항연산자 : 피연산자가 2개
>
> 삼항연산자 : 피연산자가 3개

```java
-2-5
//단항연산자: 부호연산자(-2의 -부호연산자)
//이항연산자: 뺄셈연산자(-2,-5의 -산술연산자)
```

<br/><br/>

### iv. 연산자의 우선순위와 결합규칙
{: .no_toc }

- **연산자의 우선순위**

> 아래는 일반적인 상식선에서 해결되는 순서이다
>
> **산술**(덧셈/나눗셈 - 곱셈/나눗셈) - **비교** - **논리** - **대입**
>
> **단항 - 이항 - 삼항**

```java
-x+3
//부호 - 덧셈
x+3*y
//곱셈 - 덧셈
X+3 > y-2
//덧셈 - 뺄셈 - 비교
x > 3 && x < 5
//비교 - 논리
result = x+y*3
//곱셈 - 덧셈 - 대입
```

<br/>

{: .highlight-title }
> 🥕
>
> 아래는 주의해야 할 연산자 우선순위이다

```java
x << 2+1
// x << (2+1)
```

> 덧셈/뺄셈 - 쉬프트

```java
data & 0xFF == 0
// data & (0xFF == 0)
```

> 비교 - 비트

```java
x<-1 || x>3 && x<5
//x<-1 || (x>3 && x<5)
```

> and - or

<br/>

- **연산자의 결합규칙**

> 연산자는 대부분 왼쪽에서 오른쪽의 순서로 수행한다
>
> 단, 단항연산자, 대입연산자 제외

<br/><br/>

### v. 산술 변환
{: .no_toc }

> 연산 전에 피연산자의 타입이 자동적으로 형변환되는 것 (쉬프트연산자, 증감연산자 제외)
>
> 일반 산술 변환은 아래 규칙을 따른다
>
> 1. 두 피연산자의 타입을 보다 큰 타입으로 일치시킨다
>
> 2. 피연산자의 타입이 int보다 작으면 int로 변환시킨다

```
byte + short -> int + int
```

---

## 단항 연산자

### i. 증감 연산자
{: .no_toc }

- **증감연산자란?**

> 증가연산자(++): 피연산자의 값을 1 증가시킨다
>
> 감소연산자(--): 피연산자의 값을 1 감소시킨다

<br/>

- **전위형과 후위형**

> 전위형(++i, --i): 값 증가 후 참조
>
> 후위형(i++, i--): 값 참조 후 증가

```java
j = ++i; 
//++i;
//j = i;

j = i++;
//j = i;
//i++;
```

<br/>

{: .note-title }
> 전위형과 후위형 예시
>
> 아직 헷갈리므로 출력을 통해 둘의 차이를 확인해보자

```java
class Main {
  public static void main(String[] args) {
    int i = 5;
    int j = 5;
    
    System.out.println(i++); //i에 저장된 값을 넘겨준 후 증가함
    System.out.println(++j); //j값을 증가한 뒤 값을 넘겨줌
    System.out.printf("i=%d, j=%d", i, j); //i도 증가한 모습
  }
}
```

```java
5
6
i=6, j=6
```


{: .warning-title }
> ❗️
>
> 1. 증감연산자를 최소화할 것
>
> 2. 식에 두 번 이상 포함된 변수에 증감연산자의 사용은 자제할 것

<br/><br/>

### ii. 부호 연산자
{: .no_toc }

> 부호연산자는 +와 -가 있지만 실질적으로 +는 사용하지 않는다
>
> 또한, boolean과 char을 제외한 기본형에만 사용할 수 있다

---

## 산술 연산자

### i. 사칙 연산자
{: .no_toc }

> +, -, /, *이 있으며, 숫자뿐만 아니라 문자에도 유니코드를 통해 사칙연산자를 사용할 수 있다
>
> 사칙연산은 상식선에서 알고있는 것들이기 때문에 주의해야할 점을 정리한다

<br/>

- **형변환**

1. int형보다 작은 두 타입의 연산과 식

```java
byte a = 10;
byte b =20;

byte c = (a + b);
//byte = int + int 이므로 에러발생

byte c = (byte) (a + b);
```

<br/>

{:style="counter-reset:none"}
2. 오버플로우

```java
long a = 1_000_000 * 1_000_000; //오버플로우 발생
long b = 1_000_000 * 1_000_000L;
```

> **필요로 하는 명시적 형변환을 해주지 않을 경우 오버플로우가 발생할 수 있다**
> 
> a의 경우 int형끼리 계산한 값이기 때문에 오버플로우가 발생한다
>
> b의 경우 long타입이 하나 껴있으므로 자동형변환에 의해 올바른 값을 구할 수 있다

<br/>

```java
int a = 1_000_000;

int result1 = a * a / a; //오버플로우 발생
int result2 = a / a * a;
```

> **사칙연산의 순서에 의해 오버플로우가 발생할 수 있다**
>
> result2는 result1과 다르게 연산과정에서 int형 타입의 범위를 벗어나지 않았기 때문에 정상값이 출력된다

<br/>

{:style="counter-reset:none"}
3. 문자의 사칙연산

> 문자는 유니코드로 해석되기 때문에 정수간의 연산과 동일하게 수행 가능하다

```java
char c1 = 'a'; //97로 저장
char c2 = c1;
char c3 = ' ';

int i = c1 + 1; //97 + 1 = 98
System.out.println("i  = " + i);

c3 = (char) (c1 + 1);
System.out.println("c3 = " + c3);
		
c2++;
c2++;
System.out.println("c2 = " + c2);
```

```java
i  = 98
//int형으로 계산하니 숫자로 나오는 모습

c3 = b
//문자형으로 계산하니 문자로 나오는 모습

c2 = c
//97+2=99로 해당 유니코드의 문자 c가 출력된 모습
```

<br/>

{:style="counter-reset:none"}
4. 변수가 들어간 사칙연산

> 상수 또는 리터럴 간의 연산은 컴파일 시에 이루어진다
>
> 따라서 변수가 들어간 수식은 컴파일러가 미리 계산을 할 수 없기 떄문에 형변환이 필요하다

```java
char c1 = 'a';

char A = c1 + 1; //컴파일 에러
char B = 'a' + 1;
```

```java
char A = (char) (c1+ 1);
```

<br/>

{:style="counter-reset:none"}
5. int형의 반올림과 버림

> int형 끼리의 나눗셈의 결과는 int형이다
>
> 따라서 소수점 이하의 숫자는 버려진다는 것을 주의해야 한다

```java
float PI = 3.141592f;

float A = (int) (PI * 1000) / 1000f;
System.out.println(A);
```

```java
3.141
```

{: .note-title }
> 🥕
>
> 만약 반올림 값을 얻고싶으면 어떻게 해야 할까?
>
> **round 매서드를 사용하면 된다**

```java
double B = Math.round(PI * 1000) / 1000.0
```

<br/><br/>

### ii. 나머지 연산자
{: .no_toc }

> **%**를 사용하여 왼쪽 피연산자를 오른쪽 피연산자로 나눈 나머지 값을 결과로 반환한다
>
> 오른쪽 피연산자의 부호는 무시된다

```java
System.out.println(-10 % 8);
System.out.println(10 % -8);
System.out.println(-10 % -8);
```

```java
-2
2
-2
```

---

## 비교 연산자

### i. 대소비교 연산자
{: .no_toc }

> 값의 크기를 비교하는 연산자로 **>, < , <=, >=**가 있다
>
> boolean형을 제외한 기본형에 사용가능하며 값은 true, false로 반환한다

<br/><br/>

### ii. 등가비교 연산자
{: .no_toc }

- **숫자 및 문자의 비교**

> 값이 같은지 다른지를 비교하는 연산자로 **==, !=**가 있다

```java
System.out.printf("0 == '0'    %b%n", 0=='0');
System.out.printf("'A' == 65   %b%n", 'A'==65);
System.out.printf("10 != 10.0f %b%n", 10 != 10.0f);
```

```java
0 == '0'    false
'A' == 65   true
10 != 10.0f false //10.0f로 자동형변환
```

<br/>

- **문자열의 비교**

> 문자열은 **equals()** 매소드를 사용하며
>
> 대소문자 구분없이 비교하고 싶을 땐 **equalsIgnoreCase()**를 사용한다
>
> 아래 equals매소드 없이 등가비교하면 어떻게 되는지 알아보자

```java
String str1 = "abc";
String str2 = new String("abc");

System.out.printf("str1 == \"abc\" %b%n", str1 == "abc");
System.out.printf("str2 == \"abc\" %b%n", str2 == "abc");
```

```java
str1 == "abc" true
str2 == "abv" false
```

> 위처럼 같은 문자열을 갖더라도 서로 다른 객체라면 false로 출력한다
>
> 이번엔 동일한 등가비교에 equals 매소드를 사용해보자

```java
System.out.printf("str1.equals(\"abc\") %b%n", str1.equals("abc"));
System.out.printf("str2.equals(\"abc\") %b%n", str2.equals("abc"));
```

```java
str1.equals("abc") true
str2.equals("abc") true
```

---

## 논리 연산자

> 비교연산자와 결합하여 쓰이는 경우가 많으며 아래 기호로 표현한다

```java
char c1 = 'C';

System.out.printf("c1 < 'a' || c1 > 'z'    %b%n", c1 < 'a' || c1 > 'z');
System.out.printf("!('a' < c1 && c1 < 'z') %b%n", !('a' < c1 && c1 < 'z'));
```

```java
c1 < 'a' || c1 > 'z'    true
!('a' < c1 && c1 < 'z') true
```

{: .important-title }
> 💡
>
> &&연산자는 피연산자의 왼쪽부터 참거짓을 판별하고,
>
> 그 값이 왼쪽 피연산자에서 확정이 된다면 더이상 연산하지 않고 결과값을 반환한다
>
> 따라서 **그 값이 맞을 확률이 높은 피연산자를 왼쪽에 두자**

---

## 그 외의 연산자

### i. 조건 연산자
{: .no_toc }

> 세개의 피연산자를 필요로 하는 삼항연산자로 아래처럼 표현한다
>
> (조건식) ? (식1) : (식2)
>
> 조건식이 참이면 식1로 거짓이면 식2로 반환한다

```java
int x = 10;

int i = (x > 0) ? 0 : 1;
System.out.println(i);
```

<br/><br/>

### ii. 대입 연산자
{: .no_toc }

> **=**을 사용하여 오른쪽 피연산자의 값을 왼쪽 피연산자에 저장한다
>
> 단, 상수나 리터럴은 왼쪽 피연산자 위치에 올 수 없다

<br/>

- **복합 대입 연산자**

| 복합대입연산자 |    해석    |
|:----------:|:----------:
| i += 3 | i = i + 3 |
| i -= 3 | i = i - 3 |
| i *= 3 | i = i * 3 |
| i /= 3 | i = i / 3 |
| i %= 3 | i = i % 3 |
| i <<= 3 | i = i << 3 |
| i >>= 3 | i = i >> 3 |
| i *= 10 + j | i = i * (10 + j) |