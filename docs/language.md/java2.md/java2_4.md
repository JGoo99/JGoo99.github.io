---
layout: default
title: 배열
parent: Java 심화
grand_parent: Language
nav_order: 5
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

# IV. 배열
{: .no_toc }

---

## 배열(array)

### i. 배열이란?
{: .no_toc }

> 같은 타입의 여러 변수를 하나의 묶음으로 다루는 것

<br/><br/>

### ii. 배열의 선언과 생성
{: .no_toc }

- **배열의 선언**

> **타입[] 변수이름;**
>
> 생성된 배열을 다루기 위한 참조변수(score/name)를 위한 **공간을 만드는 것**으로
>
> 타입 변수이름[]도 가능하나 대괄호는 타입의 일부이므로 위 처럼 선언하도록 한다

```java
int[] score; //배열 score
String[] name; //배열 name
```

<br/>

- **배열의 생성**

> **변수이름 = new 타입[길이];**
>
> 값을 저장하기 위한 공간을 만드는 것이다

```java
int[] score;
score = new int[5]; //길이가 5인 int배열, 배열 score

int[] score = new int[5]; //한줄에 선언 가능하다
```

{: .note-title }
> 🥕
>
> 배열의 요소는 자동적으로 기본값인 0으로 초기화 된다

<br/><br/>

### iii. 배열의 길이와 인덱스
{: .no_toc }

- **배열의 길이**

1. 정의

> 배열 요소의 개수, 즉 **값을 저장할 수 있는 공간의 개수**이다
>
> int 타입 범위 안에 드는 양의 정수(0 포함)를 입력할 수 있다

```java
타입[] 변수이름 = new 타입[길이];

int[] arr = new int[7];

int[] num = new int[0];
```

{: .important-title }
> 🐷
>
> 아직은 잘 모르지만 길이가 0인 배열도 유용하게 사용할 수 있다고 한다
>
> 지금은 길이가 0인 배열도 선언할 수 있다는 것 정도만 알아두자

<br/>

{:style="counter-reset:none"}
2. 배열이름.length

> 배열의 길이에 대한 정보를 얻을 수 있는 **상수**이다

```java
for (int i = 0; i < score.length; i++) {
  System.out.println(score[i]);
}
```

<br/>

{:style="counter-reset:none"}
3. 배열의 길이 변경하기

> 배열은 한번 선언하고 나면 길이를 변경할 수 없다 따라서 아래와 같은 방법으로 변경해야 한다
>
> 1. 더 큰 배열을 새로 생성한다
>
> 2. 기존 배열의 내용을 새로운 배열에 복사한다

{: .highlight-title }
> 🤔
>
> 위와 같은 방법은 비용이 많이 들기 때문에
>
> 처음부터 배열의 길이를 **2배 정도 넉넉하게 선언**하는 것이 좋다


<br/>

- **배열의 인덱스**

> 배열의 요소마다 붙여진 일련번호로 0부터 시작하여 '배열길이-1' 까지의 값을 가진다
>
> 배열의 인덱스로 변수나 수식도 사용할 수 있으나 범위를 벗어나지 않도록 주의해야 한다

```java
int k = 1;
int tmp;

int[] score = new int[3];

score[0] = 10;
score[1] = 20;
score[1+k] = 30; //인덱스를 변수가 포함된 수식으로 설정

tmp = score[1] + score [1+k];

for (int i = 0; i < 3; i++) {
  System.out.printf("score[%d] = %d%n", i, score[i]);
}
System.out.println(tmp);
System.out.printf("score[%d] = %d", 4, score[4]);
```

```java
score[0] = 10
score[1] = 20
score[2] = 30
50
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 4 out of bounds for length 3
  at Main.main(Main.java:20)
```

{: .warning-title }
> Error
>
> 범위 밖의 인덱스로 배열을 호출해서(score[4]) 실행 시 위와 같은 오류가 발생한다
> 
> 변수로 설정된 인덱스는 컴파일에서 경고문이 뜨지 않으므로 범위 밖 인덱스를 설정해도 실행 전까지 알아내기가 어렵다

<br/><br/>

### iv. 배열의 초기화
{: .no_toc }

- **배열의 초기화 방법**

> 배열의 초기화 하는 방법은 다양하며 상황에 맞게 사용하면 된다
>
> 아래 여러가지 예시를 통해 알아보자

_**ex1)** 각 요소에 직접 초기화 하는 경우_

```java
int[] score = new int[5];

score[0] = 50;
score[1] = 90;
score[2] = 60;
score[3] = 80;
score[4] = 20;
```

<br/>

_**ex2)** 저장 값이 일정한 규칙을 가진 경우_

> 일정한 규칙을 가진 배열은 for문을 이용하여 초기화하면 좋다

```java
int num = new int[5];

for (int i = 0; i < num.length; i++) {
  num[i] = 20 * i + 30;
}
```

<br/>

_**ex3)** 각 요소를 한 번에 직접 초기화하는 경우_

> 배열 길이를 선언하지 않아도 괄호 안의 값의 수에 맞추어 자동으로 결정된다

```java
int score = new int[] {10, 20, 30};
int score = {10, 20, 30}; //new int[] 생략 가능
```

{: .important-title }
> ❗️
>
> 단 배열의 선언과 생성을 따로하는 경우에는 **new 타입[]**을 생략할 수 없다

```java
int[] score;
score = new int[] {10, 20, 30};
```

<br/>

_**ex4)** 배열이 add 매서드의 매개변수로 쓰이는 경우_

> 이 경우에는 **new 타입[]을 생략할 수 없다**

```java
int add(int[] arr) { /* 내용 생략 */ }

int result = add(new int[] {10, 20, 30});
```

<br/>

_**ex5)** 길이가 0인 배열을 초기화하는 경우_

```java
int[] score = new int[0];
int[] score = new int[] {};
int[] score = {};
```

<br/>

- **배열의 출력 방법**

1. **for문 사용하기**

> 일정한 규칙을 가진 값을 배열에 저장할 때도 for문을 사용하였는데
>
> 배열의 값을 출력할 때도 유용하게 사용할 수 있다
>
> 단, println()보다 print()출력을 통해 배열의 값을 한 눈에 볼 수 있게 하는 것이 좋다

```java
int[] arr = {10, 20, 30};

for (int i = 0; i < arr.length; i++) {
	System.out.print(arr[i] + " ");
}  
```

```java
10 20 30
```

<br/>

{:style="counter-reset:none"}
2. **Arrays.toString(변수이름) 매서드 사용하기**

> for문보다 더 간단한 방법으로 배열을 출력하는 방법이다
>
> [arr[0], arr[1], ... , arr[n]] 의 문자열 형식으로 반환한다

```java
int[] arr = {10, 20, 30};

System.out.println(Arrays.toString(arr));
```

```java
[10, 20, 30]
```

<br/>

{: .note-title }
> 🧐
>
> 만약 매서드 없이 배열명으로 출력하면 어떻게 될까?

```java
System.out.println(arr);
```

```java
[I@2f7c7260
```

> arr는 참조변수이므로 내부주소를 포함한 **타입@주소**형태로 출력한다
>
> I는 1차원 배열임을 나타내며, @ 뒤의 주소는 실제주소가 아닌 배열의 내부주소이다

<br/>

> _참고로 char 배열은 변수명으로 출력해도 각 요소가 정상출력된다(구분자 없음)_

```java
char[] charr = { 'a', 'b', 'c'};

System.out.println(charr);
```

```java
abc
```

<br/><br/>

### v. 배열의 복사
{: .no_toc }

> 배열은 한 번 선언할 때 그 길이까지 같이 선언되며, 길이의 변경이 불가능하다
>
> 따라서 저장공간이 더 넓은 새로운 배열을 선언하여 기존 배열을 복사하는 과정을 통해 길이 변경이 가능하다

<br/>

1. **for문 이용하기**

```java
int[] arr1 = new int[] {10, 20, 30};
System.out.println("arr1 = " + Arrays.toString(arr1));

int[] arr2 = new int[arr1.length * 2]; //기존의 길이*2

for (int i = 0; i < arr1.length; i++) { //arr2에 복사하기
  arr2[i] = arr1[i];
}

arr1 = arr2; //다시 arr1에 arr2값을 저장하여 길이 변경하기

System.out.println("arr1 = " + Arrays.toString(arr1));
```

```java
arr1 = [10, 20, 30] //기존 arr1은 사용할 수 없는 배열이 된다
arr1 = [10, 20, 30, 0, 0, 0]
```

<br/>

{:style="counter-reset:none"}
2. **System.arraycopy()매서드 이용하기**

> **System.arracopy(기존배열명, 몇 번째 요소부터, 새로운 배열명, 몇 번째 요소로, 값의 개수);**
>
> for문은 각 요소 하나하나에 접근하여 복사했다면,
>
> 위 메서드는 배열 묶음 통째로 복사하기 때문에 더 효율적이라고 할 수 있다

```java
int[] arr1 = new int[] {10, 20, 30};

int[] arr2 = new int[arr1.length * 2];

System.out.println("arr1 = " + Arrays.toString(arr1));

System.arraycopy(arr1, 0, arr2, 0, arr1.length);
arr1 = arr2;

System.out.println("arr1 = " + Arrays.toString(arr1));
```

<br/>

{: .highlight-title }
> 🐷
>
> 새로운 배열의 중간 인덱스의 위치로 복사해보자

```java
int[] arr1 = new int[] {10, 20, 30};

int[] arr2 = new int[arr1.length * 2];

System.out.println("arr1 = " + Arrays.toString(arr1));

System.arraycopy(arr1, 0, arr2, 2, arr1.length);
arr1 = arr2;

System.out.println("arr1 = " + Arrays.toString(arr1));
```

<br/><br/>

### vi. 배열의 활용
{: .no_toc }

> 아래의 다양한 예제들을 통해 배열을 어떻게 활용해야할지 배워보자

<br/>

_**ex1)** 배열 요소의 총합과 평균 구하기 예제_

```java
int sum = 0;

int[] score = {100, 88, 100, 100, 90};

for (int i = 0; i < score.length; i++) {
  sum += score[i];
}

System.out.println("sum = " + sum);
System.out.println("average = " + (float)sum/score.length);
```

```java
sum = 478
average = 95.6
```

<br/>

_**ex2)** 배열의 요소 중 최대값과 최소값 구하기 예제_

```java
int[] score = {79, 88, 91, 33, 100, 55, 95};
int max = score[0];
int min = score[0];

for (int i = 0; i < score.length; i++) {
  if (max < score[i]) {
    max = score[i];
  } else if (min > score[i]) {
    min = score[i];
  }
}

System.out.println("max = " + max);
System.out.println("min = " + min);
```

```java
max = 100
min = 33
```

<br/>

_**ex3)** 배열 요소의 순서 섞기 예제_

```java
int[] numArr = new int[10];
int random;

for (int i = 0; i < numArr.length; i++) {
  numArr[i] = i;
}
System.out.println(Arrays.toString(numArr));

for (int j = 0; j < numArr.length; j++) {
  random = (int) (Math.random()*10);
  int tmp = numArr[j];
  numArr[j] = numArr[random];
  numArr[random] = tmp;
}
System.out.println(Arrays.toString(numArr));
```

```java
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
[3, 4, 6, 2, 9, 0, 5, 8, 1, 7]
```

<br/>

{: .warning-title }
> ❗️
>
> x의 값과 y의 값을 바꿀 때는 아래처럼 해야한다

```java
tmp = x;
x = y;
y = tmp;
```

<br/>

_**ex4)** 연속 or 불연속적인 값들로 배열 초기화하기 예제_

1. **연속적인 값(로또번호)**

```java
int[] num = new int[45];
int[] lotto = new int[6];

Random rd = new Random();

for (int i = 0; i < num.length; i++) { //1-45 배열 생성
  num[i] = (i+1);
}

for (int i = 0; i < num.length; i++) { //num[] 배열 섞기
  int tmp = num[i];
  num[i] = num[rd.nextInt(45)];
  num[rd.nextInt(45)] = tmp;
}

for (int i = 0; i < 6; i++) { //lotto[] 배열 생성하여 복사
  lotto[i] = num[i];
}

System.out.println(Arrays.toString(lotto));
```

```java
[33, 7, 43, 20, 45, 23]
```

<br/>

{: .important-title } 
> 🐷
>
> **난수를 생성하는 방법**
>
> 1. Math.random() * n + 1
>
> 2. random.nextInt(n) + 1

<br/>

{:style="counter-reset:none"}
2. **불연속적인 값(임의의 수)**

```java
int[] num = {-1, 4, 6, -5 ,7};
int[] arr = new int[10];

for (int i = 0; i < arr.length; i++) {
  arr[i] = num[(int) (Math.random()*5)];
}
System.out.println(Arrays.toString(arr));
```

```java
[-1, 6, -1, 7, -5, 4, -1, 4, 6, 6]
```

<br/>

_**ex5)** 오름차순, 내림차순으로 배열 정렬하기 예제_

```java
int[] num = new int[10];

for (int i = 0; i < num.length; i++) { //1-10까지 무작위 저장
  num[i] = (int) (Math.random() * 10 + 1);
}
System.out.println("무작위 결과:\n" + Arrays.toString(num));
System.out.println();

for (int i = 0; i < num.length; i++) { 
  boolean check = false;

  for (int j = 0; j < num.length-1-i; j++) { 
    if (num[j] > num[j+1]) {
      int tmp = num[j];
      num[j] = num[j+1];
      num[j+1] = tmp;
      check = true;
      continue;
    }
  }

  if (!check) { //자리 바꾸지 않았으면 종료
    System.out.println();
    break;
  } else {      //자리 바꿨으면 계속 진행
    System.out.println(Arrays.toString(num));
  }
}
System.out.println("정렬 결과:\n" + Arrays.toString(num));
```

```java
무작위 결과:
[2, 7, 1, 4, 1, 7, 1, 7, 8, 2]

[2, 1, 4, 1, 7, 1, 7, 7, 2, 8]
[1, 2, 1, 4, 1, 7, 7, 2, 7, 8]
[1, 1, 2, 1, 4, 7, 2, 7, 7, 8]
[1, 1, 1, 2, 4, 2, 7, 7, 7, 8]
[1, 1, 1, 2, 2, 4, 7, 7, 7, 8]

정렬 결과:
[1, 1, 1, 2, 2, 4, 7, 7, 7, 8]
```

<br/>

{: .important-title }
> ❗️
>
> 중요한 것은 **반복 횟수(for문의 조건식)**이다
>
> 전체 비교횟수는 **num.length-1**이고, 각 자리를 하나하나 비교하는 횟수는 **num.length-1-i**이다
>
> 최대값, 그 다음 최댓값을 하나씩 찾아 뒤로 밀어내는 과정이라고 생각하면 쉽다
>
> 큰 값이 자기 자리를 찾아가면 그 자리의 수는 비교하지 않아도 된다 (-i)

<br/>

_**ex6)** 배열 특정 요소의 빈도수 구하기 예제_

1. 내가 푼 답안

> 책의 답안에 더 효율적인 방법이 있으나, 비교를 통한 학습을 위해 기록한다

```java
int[] num = new int[10];

for (int i = 0; i < num.length; i++) {
  num[i] = (int) (Math.random()*10 + 1);
}
System.out.println(Arrays.toString(num));

for (int i = 1; i < num.length+1; i++) {
  int sum = 0;
  for (int j = 0; j < num.length; j++) {
    if (num[j] == i) {
      sum++;
      continue;
    }
  }
  System.out.printf("%2d의 빈도 = %d%n",i, sum);
}
```

```java
[10, 7, 4, 7, 7, 3, 2, 4, 4, 6]
 1의 빈도 = 0
 2의 빈도 = 1
 3의 빈도 = 1
 4의 빈도 = 3
 5의 빈도 = 0
 6의 빈도 = 1
 7의 빈도 = 3
 8의 빈도 = 0
 9의 빈도 = 0
10의 빈도 = 1
```

<br/>

{:style="counter-reset:none"}
2. 책의 답안

> 같은 길이의 새로운 배열을 선언하여 빈도수를 세는 방법이다
>
> num[i]의 해당하는 숫자 -> counter[i-1]에 값을 1씩 증가시키는 과정을 반복하여 저장
>
> 아래 과정을 보고 이해해보자

```java
counter[1-1= 0]++
counter[7-1= 6]++
counter[3-1= 2]++
counter[5-1= 4]++

//이런식으로 counter배열의 값이 1씩 증가하여 빈도수를 셀 수 있다
```

<br/>

```java
int[] num = new int[10];
int[] counter = new int[10];

//중략

for (int i = 0; i < num.length; i++) {
  counter[num[i]-1]++;
}

for (int i = 0; i < num.length; i++) {
  System.out.printf("%2d의 빈도: %d%n", i+1, counter[i]);
}
```

```java
[1, 7, 3, 5, 8, 4, 2, 3, 10, 6]
 1의 빈도: 1 
 2의 빈도: 1 
 3의 빈도: 2
 4의 빈도: 1
 5의 빈도: 1
 6의 빈도: 1
 7의 빈도: 1 
 8의 빈도: 1
 9의 빈도: 0
10의 빈도: 1
```

---

## String배열

### i. String배열의 선언과 생성
{: .no_toc }

- **String배열의 선언**

> 생성방법은 int배열과 다르지 않으며, 기본값은 null이다
>
> _각 자료형의 기본값을 정리한 링크를 아래에 첨부한다_

```java
String[] name = new String[3];
```

> String은 참조형 자료이므로 null값이 기본값이 된다

[Link button](https://jgoo99.github.io/docs/language.md/java2.md/java2_1/#ii-%EB%B3%80%EC%88%98%EC%9D%98-%EC%84%A0%EC%96%B8%EA%B3%BC-%EC%B4%88%EA%B8%B0%ED%99%94){: .btn .btn-outline }

<br/><br/>

### ii. String배열의 초기화
{: .no_toc }

- **기본 초기화 방법**

> int형 배열과 초기화 방법이 다르지 않다

```java
String[] name = new String[3];

name[0] = new String("Hong");
name[1] = new String("Gil");
name[2] = new String("Dong");
```

{: .highlight-title }
> 🥕
>
> String은 클래스이므로 원래는 위 처럼 선언해야하며, 아래처럼 생략하여 표현하는 것도 허용된다

```java
name[0] = "Hong";
name[1] = "Gil";
name[2] = "Dong";
```

<br/>

- **간단한 초기화 방뻡**

> String배열 역시 new String[]을 생략하여 간단하게 선언할 수 있다
>
> 단, 참조형 배열의 경우 참조형 자료이므로 배열에 저장되는 것은 값이 아닌 객체의 주소이다 (객체배열)

```java
String[] name = new String[] {"Hong", "Gil", "Dong"};

String[] name = {"Hong", "Gil", "Dong"};
```

<br/><br/>

### iii. char배열과 String클래스
{: .no_toc }

- **정의**

> String클래스는 char배열에 매서드 기능을 추가한 것이다
>
> 둘의 **중요한 차이점은 String객체(문자열)는 읽을 수만 있을 뿐 내용을 변경할 수 없다**
>
> (+객체지향개념이 나온 후 자바에서는 데이터와 그에 관련된 기능(매서드)들을 하나의 클래스로 묶어 사용한다)

```java
String str = "java";
str = str + "11";
System.out.println(str);
```

```java
java11
```

> 문자열을 변경한 것 같지만 **새로운 문자열을 생성**하여 저장한 것이다

<br/>

- **String클래스의 주요 매서드**

```java
String str = "ABCDE";
char ch = str.charAt(3);
System.out.println(ch);
```

```java
D
```

> 문자열에서 해당 위치(index)에 있는 문자를 반환한다

<br/>

```java
String str = "ABCDE";
int i = str.length();
System.out.println(i);
```

```java
5
```

> 문자열의 길이를 반환한다

<br/>

```java
String str = "ABCDE";
String str2 = str.substring(2,4);
System.out.println(str2);
```

```java
CD
```

> 문자열에서 해당 범위(from-to)에 있는 문자열을 반환한다 (**to는 미포함**)

<br/>

```java
String str1 = "ABCDE";
String str2 = "ABCDE";

if (str1.equals(str2)) System.out.println(str2);
```

```java
ABCDE
```

> 문자열의 내용이 같은지 확인한다 (같으면 true, 다르면 false)

<br/>

```java
String str = "ABCDE";
char[] ch = str.toCharArray();
System.out.println(Arrays.toString(ch));
```

```java
[A, B, C, D, E]
```

> 문자열을 문자배열(char[])로 변환해서 반환한다
>
> 이 부분은 아래에서 더 자세히 다룬다


<br/>

- **char배열과 String클래스의 변환**

1. **단순 변환 방법**

_char배열 - String클래스_

```java
String str = new String(chArr);
```

_String클래스 - char배열_

```java
char[] chArr = str.toCharArray();
```

<br/>

{:style="counter-reset:none"}
2. **String-char 예제**

_**ex1)** 문자열을 char배열로 변환하여 하나씩 출력하기 예제_

```java
String src = "ABCD";

for (int i = 0; i < src.length(); i++) {
  char ch = src.charAt(i);
  System.out.printf("src.charAt(%d) :%c%n", i, ch);
}

char[] chArr = src.toCharArray();
System.out.println(chArr);
```

```java
src.charAt(0) :A
src.charAt(1) :B
src.charAt(2) :C
src.charAt(3) :D
ABCD
```

> **length(), charAt(int idx), toCharArray()**가 쓰인 것을 알 수 있다
>
> 또한, char배열은 바로 출력해도된다 **System.out.print(chArr)**

<br/><br/>

### iv. 커맨드 라인을 통해 입력받기
{: .no_toc }

> 터미널에서 커맨드라인을 이용하여 배열의 요소를 전달할 수 있다.

```java
class Main {
  public static void main(String[] args) {
    System.out.printf("매개변수의 개수: %d%n", args.length);
    for (int i = 0; i < args.length; i++) {
      System.out.printf("args[%d] = %s%n", i, args[i]);
    }
  }
}
```

_~/algorithm/javatutorial/src_
```
> java Main abc 123 "Hello World"
매개변수의 개수: 3
args[0] = abc
args[1] = 123
args[2] = Hello World

> java Main
매개변수의 개수: 0
```

<br/>

_ex) 커맨드라인을 통해 계산해보기_

```java
class Main {
  public static void main(String[] args) {
    if (args.length != 3) {
      System.out.println("usage: java Main NUM1 OP NUM2");
      System.exit(0);
    }

    int NUM1 = Integer.parseInt(args[0]);
    char OP = args[1].charAt(0);
    int NUM2 = Integer.parseInt(args[2]);
    int result = 0;

    switch (OP) {
      case '+':
        result = NUM1 + NUM2;
        break;
      case '-':
        result = NUM1 - NUM2;
        break;
      case '/':
        result = NUM1 / NUM2;
        break;
      case 'x':
        result = NUM1 * NUM2;
        break;
      default:
        System.out.println("지원하지 않는 연산입니다.");
    }
    System.out.printf("%d %c %d = %d", NUM1, OP, NUM2, result);
  }
}
```

```sh
> java Main
usage: java Main NUM1 OP NUM2

>java Main 1 + 2
1 + 2 = 3%

> java Main 1 - 3
1 - 3 = -2%

> java Main 4 / 2
4 / 2 = 2%

> java Main 4 x 6
4 x 6 = 24%
```

---

## 다차원 배열

### i. 2차원 배열의 선언과 인덱스
{: .no_toc }

> **타입[][] 변수이름 = new 타입[n][m];** 으로 n행 m열의 배열을 생성할 수 있다.

```java
int[][] score = new int[1][2];
```

| | 1열 | 2열 | 3열 |
|:---:|:---:|:---:|:---:|
| 1행 | score[0][0] | score[0][1] | score[0][2] |
| 2행 | score[1][0] | score[1][1] | score[1][2] |

_아직 초기화하지 않았기 때문에 배열의 각 요소의 값은 0이다._

<br/><br/>

### ii. 2차원 배열의 초기화
{: .no_toc }

> 2차원 배열은 **배열의 배열**로 구성되어 있다.

```java
int[][] score = {
  {1,2,3},
  {4,5,6}
};

System.out.println(score[1][2]);
```

```java
6
```

<br/>

_**ex 1)** 배열을 모두 출력하고, 그 합을 구해라._ 

```java
class Main {
  public static void main(String[] args) {
    int[][] score = {
            {100, 100, 100},
            {20, 20, 20},
            {30, 30, 30},
            {40, 40, 40}
    };

    int sum = 0;

    for (int i = 0; i < score.length; i++) { //score.length = 4
      for (int j = 0; j < score[i].length; j++) {
        System.out.printf("score[%d][%d]= %3d%n", i, j, score[i][j]);
        sum += score[i][j];
      }
    }
    System.out.printf("sum = %d", sum);
  }
}
```

```java
score[0][0]= 100
score[0][1]= 100
score[0][2]= 100
score[1][0]=  20
score[1][1]=  20
score[1][2]=  20
score[2][0]=  30
score[2][1]=  30
score[2][2]=  30
score[3][0]=  40
score[3][1]=  40
score[3][2]=  40
sum = 570
```

<br/>

{: .note }
> 배열+반복문의 문법 for each 문

```java
for (int[] tmp : score) {  //tmp에 score의 각 요소(1차원 배열의 주소)를 저장
  for (int i : tmp) {      //tmp는 1차원 배열을 가리키는 참조변수 
    sum += i;
  }
}
```

> 먼저 tmp에 {100, 100, 100}, {20, 20, 20} ... 이 각각 담긴다
>
> 각각의 tmp의 각 요소를 다시 차례로 i에 담는다

<br/>

_**ex 2)** 5명의 세 과목 점수를 더해서 각 학생의 총점, 평균과 과목별 총점을 계산해라._ 

```java
class Main {
  public static void main(String[] args) {
    int[][] score = {
            {100, 100, 100},
            {20, 20, 20},
            {30, 30, 30},
            {40, 40, 40},
            {50, 50, 50}
    };

    System.out.println("번호		국어		수학		영어		총점		평균");
    System.out.println("============================================");

    int kor = 0;
    int math = 0;
    int eng = 0;

    for (int i = 0; i < score.length; i++) {
      System.out.print(i+1);
      int sum = 0;
      float avg = 0.0f;

      kor += score[i][0];
      math += score[i][1];
      eng += score[i][2];

      for (int j = 0; j < score[i].length; j++) {
        sum += score[i][j];
        System.out.printf("	  %5d", score[i][j]);
      }
      avg = sum/3;
      System.out.printf("	 %5d	  %5.1f%n", sum, avg);
    }
    System.out.println("============================================");
    System.out.println("총점:	" + kor + "		" + math + "		" + eng);
  }
}
```

```java
번호		국어		수학		영어		총점		평균
============================================
1	    100	    100	    100	   300	  100.0
2	     20	     20	     20	    60	   20.0
3	     30	     30	     30	    90	   30.0
4	     40	     40	     40	   120	   40.0
5	     50	     50	     50	   150	   50.0
============================================
총점:	240		240		240
```

<br/><br/>

### iii. 가변 배열
{: .no_toc }



<br/><br/>

### iv. 다차원 배열의 활용
{: .no_toc }
