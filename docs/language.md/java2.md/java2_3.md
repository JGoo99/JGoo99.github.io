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

<br/>

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

> 1. **switch문의 조건식 결과는 정수 또는 문자열이어야 한다**
>
> 2. **case문의 값은 정수 상수만 가능하며, 중복되지 않아야 한다**
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

_**ex1)** 몇 월인지 입력받은 후 계절을 출력하는 예제_

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

_**ex2)** 컴퓨터와 유저 간의 가위바위보 게임 예제_

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

_**ex3)** 주민등록번호를 입력받아 성별을 구별하는 예제_

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

_**ex4)** 점수를 입력받아 학점을 부여하는 예제_

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

1. **for문의 구조와 수행순서**

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

<br/>

- **증감식**

> 반복문을 제어하는 변수의 값을 일정하게 변화시켜, 그 값이 조건식을 벗어나면 for문을 종료하도록 한다
>
> i++, i--, i+=2, i*=3 등 복합 대입 연산자를 사용할 수 있으며 생략도 가능하다

```java
for (int i = 0; i < 10; i*=3) {} //i가 3배씩 증가

for (int i = 0, j = 9; i< 10; i++, j--) {} //i는 0부터 9까지, j는 9부터 0까지 감소

for(;;) {} //무한반복문으로 사용가능하며 if문을 통해 빠져나오도록 설계하면 된다

for(int i = 0; i < 10; i%=3) {} //i = 0, 1, 2, 0, 1, 2 ...로 반복 가능

for(int i = 0; i < 10; i/=3) {} //i = 0, 0, 1, 1, 2, 2 ...로 연속 가능
```

_복합대입연산자 링크_

[Link button](https://jgoo99.github.io/docs/language.md/java2.md/java2_2/#ii-%EB%8C%80%EC%9E%85-%EC%97%B0%EC%82%B0%EC%9E%90){: .btn .btn-outline }

<br/>

{:style="counter-reset:step-counter 1"}
2. **향상된 for문**

> 배열이나 컬렉션 내에 저장된 값이 매반복마다 하나씩 순서대로 읽혀서 변수에 저장된다
>
> 아래 구조와 예시를 보며 향상된 for문을 이해해보자

_구조_

```java
for ( 타입 변수명 : 배열 또는 컬랙션) {
  //반복할 문장
}
```

<br/>

_**ex)** 배열 출력 예제_

```java
int[] arr = {10, 20, 30, 40, 50};

for (int i = 0; i < 5; i++) {
  System.out.print(arr[i] + " ");
}
System.out.println();

for (int tmp : arr) {
  System.out.print(tmp + " ");
}  
```

```java
10 20 30 40 50
10 20 30 40 50
```

<br/><br/>

### ii. while문
{: .no_toc }

- **while문의 구조**

> for문보다 간단하며 for문이랑 완벽하게 대체 가능한 문법이지만
>
> 초기화 과정이나 증감식이 필요없는 경우 유용하게 사용가능하다
>
> (**단, 조건식은 생략 불가능하다**)

```java
for (조건식) {
  //반복을 수행할 문장
}
```

<br/>

- **while문의 예시**

<br/>

_**ex1)** 증감식 사용 주의 예시_

1. **후위형**

```java
int i = 5, j = 5;

while (i-- != 0) {
  System.out.println(i + " hello");
}

while (i != 0) { //위와 동일함
  i--;
  System.out.println(i + " hello);
}
```

```java
4 hello
3 hello
2 hello
1 hello
0 hello
```

{: .highlight }
> i--는 후위형이기 때문에 조건식이 평가된 후 1이 감소하여 4부터 출력되는 것을 알 수 있다

<br/>

{:style="counter-reset:step-counter 1"}
2. **전위형**

> 전위형 증감식을 조건식 바깥에 쓸 경우 다른 결과값을 갖는다

```java
int i = 5, j = 5;

while (--i != 0) {
  System.out.println(i + " hello");
}

System.out.println();

while (j != 0) { 
  --j;
  System.out.println(j + " hi");
}  
```

```java
4 hello
3 hello
2 hello
1 hello

4 hi
3 hi
2 hi
1 hi
0 hi
```

<br/>

_**ex2)** 각 자리 숫자 더하기 예시_

```java
class Main {
  public static void main(String[] args) {
    int num; //입력받는 다섯자리 수 12345
    int sum = 0;

    Scanner sc = new Scanner(System.in);
    num = sc.nextInt();

    while (num != 0) {
      sum += num%10;
      System.out.printf("sum = %2d, num = %d%n", sum, num);
      num /= 10;
    }
    System.out.println();
    System.out.printf("sum = %d", sum) ;
  }
}
```

```java
sum =  5, num = 12345
sum =  9, num = 1234
sum = 12, num = 123
sum = 14, num = 12
sum = 15, num = 1

sum = 15
```

{: .new-title }
> 🧐
>
> printf()에서 **%3d, %2d**등의 표현을 볼 수 있다
>
> 위 표현은 3자리 또는 2자리 정수를 표현할 때 위처럼 빈칸을 포함하여 출력한다
>
> 또한 **%03d, %02d**등의 표현은 위와 동일하나 빈칸에 0을 채워 표현한다

```java
System.out.printf("num = %3d", num);
System.out.println();
System.out.printf("num = %03d", num);
```

```java
num =   2
num = 002
```

<br/>

_**ex3)** 누적합계가 100이 넘지 않는 제일 큰 수를 구하는 예제_

```java
int i = 0; 
int sum = 0;

while ( (sum += ++i) < 100) {
  System.out.printf("i = %2d, sum = %2d%n", i, sum);
}
```

{: .warning-title }
> ❗️
>
> 1. **조건식 내에서 i++로 입력할 경우**
>
> 조건식 내에서 i=0 부터 더해지므로 sum=0부터 시작한다
>
> {:style="counter-reset:step-counter 1"}
> 2. **printf()내에서 sum+=i로 입력할 경우**
>
> 조건식에서 한 번, printf에서 한 번 총 두 번의 i가 더해진다

<br/>

_**ex4)** 더할 숫자를 입력받다가 0을 입력받으면 총 합을 구하는 예제_

```java
int num; //입력받은 수
boolean flag = true; //입력받은 숫자가 0이면 false
int sum = 0;

Scanner sc = new Scanner(System.in);

while (flag != false) {
  System.out.print(">> ");
  num = sc.nextInt();
  if (num != 0) {
    sum += num;
  } else {
    flag = false;
  }
}
System.out.println();
System.out.printf("sum = %d", sum);
```

```java
>> 11
>> 22
>> 33
>> 0

sum = 66
```

<br/><br/>

### iii. do-while문
{: .no_toc }

- **do-while문의 구조**

> while문의 변형으로 조건식과 수행해야할 블럭의 순서가 바뀌어있다
>
> 주의할 점은 **조건식 뒤 새미콜론을 잊지 않도록 한다**

```java
do {
  //수행해야 할 문장
} while (조건식);
```

<br/>

- **do-while문의 예시**

_**ex1)** Up And Down 게임 만들기 예제_

```java
int num; //입력받을 양수
int point; //램덤으로 정해질 정답

Scanner sc = new Scanner(System.in);
point = (int) (Math.random() * 100 + 1);

System.out.print("1-100 사이 양수를 입력하시오 >> ");

do {
  num = sc.nextInt();
  if (num < point) {
    System.out.print("더 큰 수를 입력하시오 >> ");
  } else if (num > point) {
    System.out.print("더 작은 수를 입력하시오 >> ");
  }
} while (num != point);

System.out.println("정답입니다");
```

```java
1-100 사이 양수를 입력하시오 >> 20
더 큰 수를 입력하시오 >> 40
더 큰 수를 입력하시오 >> 60
더 작은 수를 입력하시오 >> 52
정답입니다
```

<br/>

{: .new-title }
> 🤔
>
> Math.random()은 **0보다 크거나 같고 1보다 작은** 난수이다

<br/><br/>

### iv. break문
{: .no_toc }

> 자신이 포함된 가장 가까운 반복문을 벗어나는 문장이다
>
> 주로 if문과 함꼐 사용되어 특정 조건을 만족하면 반복문을 벗어나도록 한다
>
> 특히 while문은 if문과 break문이 항상 같이 사용된다

<br/>

_**ex)** 1씩 증가하여 더하는 누적합계가 100을 넘었을 때의 i와 sum을 출력하는 예제_

```java
int sum = 0;
int i = 0;

while (true) {
  if ( (sum += ++i) > 100 ) {
    System.out.printf("i = %2d, sum = %2d", i, sum);
    break;
  }
}
```

<br/><br/>

### v. continue문
{: .no_toc }

> 반복이 진행되는 와중에 continue문을 만나면 반복문의 끝으로 이동하여 다음 반복이 실행된다
>
> break문과 다르게 반복문을 아예 종료하는 것이 아니다
>
> **전체 반복 중에 특정 조건을 제외하고자 할 때 유용하게 사용한다**

<br/>

_**ex1)** 1-10 숫자를 출력하되 3의 배수는 제외하는 예제_

```java
for (int i = 0; i < 11; i++) {
  if (i%3 == 0) {
    continue;
  }
  System.out.print(i + " ");

//3의 배수일 경우 이 곳, 반복문의 끝으로 이동한다
}
```

```java
1 2 4 5 7 8 10
```

<br/>

_**ex2)** 메뉴를 보여주고 선택하는 예제: 잘못선택하면 다시 메뉴를 띄우며 종료는 0이다_

```java
int io; //입력받은 메뉴 번호

Scanner sc = new Scanner(System.in);

while	(true) {
  System.out.println("(1) 가");
  System.out.println("(2) 나");
  System.out.println("(3) 다");
  System.out.print("위 보기 중 하나를 선택하시오(종료: 0) >> ");
  io = sc.nextInt();

  if (io == 0) {
    System.out.println("종료합니다");
    break;
  } else if (!( 1 <= io && io <= 3 )) {
    System.out.println("잘못 입력하셨습니다");
    continue;
  }
  System.out.println("선택하신 메뉴: " + io);
}
```

```java
(1) 가
(2) 나
(3) 다
위 보기 중 하나를 선택하시오(종료: 0) >> 1
선택하신 메뉴: 1
(1) 가
(2) 나
(3) 다
위 보기 중 하나를 선택하시오(종료: 0) >> 4
잘못 입력하셨습니다
(1) 가
(2) 나
(3) 다
위 보기 중 하나를 선택하시오(종료: 0) >> 0
종료합니다
```

<br/><br/>

### vi. 이름 붙은 반복문
{: .no_toc }

> 중첩 반복문 앞에 이름을 붙이고 break문과 continue문에 이름을 지정해 줌으로써
>
> **하나 이상의 반복문을 벗어나거나 건너뛸 수 있다**

```java
Loop1 :
  for (int i = 1; i <= 9; i++) {
    for (int j = 1; j <= 9; j++) {
      System.out.printf("%d * %d = %d", i, j, i*j);
      System.out.println();
      if (j == 5) {
        continue Loop1;
        //break Loop1;
      }
    }
  }
```

_continue Loop1; 결과 (거의 쓰이지 않음)_

```java
1 * 1 = 1
1 * 2 = 2
1 * 3 = 3
1 * 4 = 4
1 * 5 = 5
2 * 1 = 2
2 * 2 = 4
.
. 중략
.
9 * 1 = 9
9 * 2 = 18
9 * 3 = 27
9 * 4 = 36
9 * 5 = 45
```

_break Loop1; 결과_

```java
1 * 1 = 1
1 * 2 = 2
1 * 3 = 3
1 * 4 = 4
1 * 5 = 5
```