---
layout: default
title: 조건문과 반복문
parent: Java 심화
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

# III. 조건문과 반복문
{: .no_toc }

- **제어문이란?**

> **코드의 흐름(flow)를 바꾸는 역할을 하는 문장**으로 조건문과 반복문이 있다

---

## 조건문

### i. if문
{: .no_toc }

- **if문의 구조**

> if문은 조건식과 괄호로 이루어져있다
>
> if문의 조건식이 true면 괄호 안의 문장을 수행하라는 의미의 문법이다

```java
if (조건식) {
  괄호 안의 문장
}
```

<br/>

1. **조건식**

> 조건식은 일반적으로 논리연산자와 비교연산자로 이루어져있으며
>
> ture 또는 false 두 가지 값만 결과값으로 가진다

<br/>

{:style="counter-reset:none"}
2. **괄호**

> 한 문장 이상의 문장들로 이루어져있으며 조건식이 true면 수행, false면 수행하지 않는다

{: .note-title }
> 🥕
>
> 괄호 안의 문장이 한 문장일 경우 아래처럼 표현할 수 있으나 
>
> 나중에 문장을 추가할 때, 괄호를 쓰지 않는 실수가 많으므로 웬만하면 괄호를 사용하도록 한다

```java
if (true) System.out.println("TRUE");

if (true)
  System.out.println("TRUE");
```

<br/><br/>

### ii. if-else 문
{: .no_toc }

> 조건식이 참일 경우의 수행할 괄호블럭과 그 밖의 경우(거짓)일 때 수행할 괄호블럭으로 이루어져있다

```java
if (조건식) {
  조건식이 참일 경우 수행
} else {
  그 밖의 경우(거짓) 수행
}
```

<br/><br/>

### iii. if-else if문
{: .no_toc }

> 처리해야 할 경우의 수가 셋 이상일 때 사용하는 문법으로
>
> 참인 조건식을 만나면 해당 괄호블럭을 수행한 후 if문을 빠져나온다

```java
if (조건식 1) {
  조건식 1이 참일 경우 수행
} else if (조건식 2) {
  조건식 2가 참일 경우에 수행
} else if (조건식 3) {
  조건식 3가 참일 경우에 수행
} else {
  참인 조건식이 없을 경우 수행 (생략가능)
}
```

<br/><br/>

### iv. 중첩 if문
{: .no_toc }

> if문 안에 if문을 포함시키는 문법으로, 중첩 횟수에는 제한이 거의 없다

```java
if (조건식 1) {
  조건식 1이 참일 경우 수행
  if (조건식 2) {
    조건식 1과 2가 모두 참일 경우 수행
  }
}
```

<br/><br/>

### v. switch문
{: .no_toc }

- **switch문은 언제 사용할까**

> if문은 참, 거짓으로 결과가 두 가지 뿐이라 여러개의 조건식이 있을 경우 복잡해진다
>
> 따라서 하나의 조건식으로 **다양한 경우의 수를 처리**할 수 있는 switch문을 사용한다

<br/>

- **switch문의 구조**

<br/>

1. **switch문의 흐름**

> 1. 조건식을 계산한다
>
> 2. 조건식의 결과와 일치하는 case문으로 이동한다
>
> 3. 이후의 문장들을 수행한다
>
> 4. break문이나 switch문의 끝을 만나면 switch문 전체를 빠져나간다

```java
switch (조건식) {
  case 값1 :
    조건식의 결과가 값1과 같을 경우 수행될 문장들
    break;
  case 값2 :
    조건식의 결과가 값2와 같을 경우 수행될 문장들
    break;
  default :
    조건식의 결과와 일치하는 case문이 없을 때 수행될 문장들
}
```

> 이떄 **default문**은 if문의 else와 같은 역할을 한다
>
> 대부분 마지막에 쓰이기 때문에 break문을 쓰지 않아도 된다

<br/>

{:style="counter-reset:none"}
2. **break문의 용도**

> switch문의 각 case문 영역을 구분하는 역할을 한다
>
> 만약 break문이 없을 경우 다른 case문의 문장들도 실행되므로 빼먹지 않도록 주의한다
>
> 그러나 필요에 따라서 의도적으로 break문을 제외하는 경우가 있다 _아래 예시_

_회원제 웹사이트 코드 일부_

```java
switch (level) {
  case 3 :
    grantDelete(); //삭제권한
  case 2 :
    grantWrite();  //쓰기권한
  case 1 :
    grantRead();   //읽기권한
}
```

> level 3일 경우 모든 권한을 갖고, level 1일 경우 읽기권한만 가질 수 있다

<br/>

{:style="counter-reset:none"}
3. **switch문의 제약조건**

> 1. switch문의 조건식 결과는 정수 또는 문자열이어야 한다
>
> 2. case문의 값은 정수 상수만 가능하며, 중복되지 않아야 한다
>
> 아래 여러가지 예시를 통해 switch문을 알아보자

<br/>

_switch문과 제약조건_

```java
int num, result;
final int ONE = 1;

switch (result) {
  case '1' :    //OK 문자상수 (숫자 49와 동일)
  case ONE :    //OK 정수상수
  case "YES" :  //OK 문자열 상수
  case num :    //ERROR 변수 불가
  case 1.0 :    //ERROR 실수 불가
} 
```

<br/>

{:style="counter-reset:step-counter 3"}
4. **switch문의 여러가지 예시**

_몇 월인지 입력받은 후 계절을 출력하는 예제_

```java
class Main {
  public static void main(String[] args) throws IOException {
    int mon; //입력받는 달

    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));

    mon = Integer.parseInt(br.readLine());
    br.close();

    switch (mon) {
      case 3 : case 4 : case 5 :
        bw.write("봄");
        break;
      case 6 :
      case 7 :
      case 8 :
        bw.write("여름");
        break;
      case 9 : case 10 : case 11 :
        bw.write("가을");
        break;
      default :  
      case 12 : case 1 : case 2 :
        bw.write("겨울");
        break;
    }
    bw.flush();
    bw.close();
  }
}
```

{: .highlight }
> case문은 한줄에 써도 되고, 붙여서 써도 된다

<br/>

_컴퓨터와 유저 간의 가위바위보 게임 예제_

```java
class Main {
  public static void main(String[] args) throws IOException {
    int user, com;

    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));

    bw.write("가위(1), 바위(2), 보(3) 중에 하나를 입력하시오 > ");
    bw.flush();
    bw.newLine();

    user = Integer.parseInt(br.readLine());
    br.close();

    com = (int) (Math.random() * 3 + 1);

    bw.write("user: " + user + "\ncom: " + com);
    bw.flush();
    bw.newLine();

    switch (user - com) {
      case -2 : case 1 :
        bw.write("user win");
        break;
      case -1 : case 2 :
        bw.write("user lose");
        break;
      case 0 :
        bw.write("retry");
    }
    bw.flush();
    bw.close();
  }
}
```

<br/>

_주민등록번호를 입력받아 성별을 구별하는 예제_

```java
class Main {
  public static void main(String[] args) {
    String regNo; //입력받는 주민등록번호
    char gender;  //성별

    Scanner sc = new Scanner(System.in);
    regNo = sc.nextLine();
    gender = regNo.charAt(7);

    switch (gender) {
      case '1': case '3':
        System.out.println("남성");
        break;
      case '2': case '4':
        System.out.println("여성");
        break;
      default:
        System.out.println("다시 입력하시오");
    }
  }
} 
```

{: .warning-title }
> Error
>
> 문자형 숫자와 정수형 숫자의 구별을 주의하자
>
> **'1'은 문자, 1은 정수형 숫자이다**
>
> 만약 case 결과값을 (1,3) (2,4)로 한다면 default값의 문장만 수행될 것이다

<br/>

_점수를 입력받아 학점을 부여하는 예제_

```java
class Main {
  public static void main(String[] args) {
    int score; //입력받는 점수
    char grade; //부여되는 학점

    Scanner sc = new Scanner(System.in);
    System.out.print("성적 입력 > ");
    score = sc.nextInt();

    switch (score/10) {
      case 10: case 9:
        grade = 'A';
        break;
      case 8:
        grade = 'B';
        break;
      case 7:
        grade = 'C';
        break;
      default:
        grade = 'F';
    }
    System.out.println("학점 : " + grade);
  }
}
```

<br/>

{:style="counter-reset:step-counter 4"}
5. **switch문의 중첩**

> 중첩은 가능하나, 가독성과 break를 빼먹는 실수 등의 단점으로 사용하지 않는 편이 좋아보인다

---

## 반복문

### i. for문
{: .no_toc }

_for문은 반복 수행 횟수를 알고있을 때 사용하면 좋다_

<br/>

1. for문의 구조와 수행순서

> 초기화, 조건식, 증감식, 블럭으로 이루어져 있으며, 수행순서는 아래와 같다
>
> 수행순서: 초기화 - 조건식(참) - 수행될 문장 - 증감식 - 다시 조건식부터 - ... - 조건식(거짓) - 종료

```java
for (초기화; 조건식; 증감식;) {
  수행될 문장
}
```

<br/>

- **초기화**

> 초기화는 처음에 한 번만 수행되며, 둘 이상의 변수를 사용할 땐 구분자;를 이용하여 선언한다

```java
for (int i = 0; i < 10; i++) {}

for (int i  = 0, j = 1; i < 10; i++) {}
```

<br/>

- **조건식**

> 조건식의 값이 참이면 반복수행, 거짓이면 for문을 종료한다
>
> 조건식을 잘못 입력하면 블럭 내 문장이 아예 수행되지 않거나 무한반복을 하는 오류가 발생할 수 있다

- **증감식**

> 

<br/><br/>

### ii. while문
{: .no_toc }

<br/>


<br/>

<br/>

<br/><br/>

### iii. do-while문
{: .no_toc }


<br/><br/>

### iv. break문
{: .no_toc }



<br/><br/>

### v. continue문
{: .no_toc }


<br/><br/>

### vi. 이름 붙은 반복문
{: .no_toc }
