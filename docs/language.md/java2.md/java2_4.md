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

```

```java

```

<br/>

{:style="counter-reset:none"}
2. **불연속적인 값(임의의 수)**

```java

```

```java

```

<br/>

_**ex5)** 오름차순, 내림차순으로 배열 정렬하기 예제_

```java

```

```java

```

<br/>

_**ex6)** 배열 특정 요소의 빈도수 구하기 예제_

```java

```

```java

```

<br/>



---

## String배열

### i. String배열의 선언과 생성
{: .no_toc }



<br/><br/>

### ii. String배열의 초기화
{: .no_toc }



<br/><br/>

### iii. char배열과 String클래스
{: .no_toc }



<br/><br/>

### iv. 커맨드 라인을 통해 입력받기
{: .no_toc }



---

## 다차원 배열

### i. 2차원 배열의 선언과 인덱스
{: .no_toc }



<br/><br/>

### ii. 2차원 배열의 초기화
{: .no_toc }



<br/><br/>

### iii. 가변 배열
{: .no_toc }



<br/><br/>

### iv. 다차원 배열의 활용
{: .no_toc }
