---
layout: default
title: 매소드
parent: Java
grand_parent: Programing
nav_order: 9
---

# VIII. 매소드

```java
public static void main(String[] args) {
  return
}
```

_지금까지 사용해온 위의 **void main** 이 곧 매소드이다_

---

## 1. 재활용성

_매소드는 반복적인 코드의 활용성을 높일 수 있다_

> 0부터 4까지 출력하는 for 문을 5번 출력해보자

```java
for (int j = 0; j < 5; j++) {
  for (int i = 0; i < 5; i++) {
	  System.out.println(i);
  }
  System.out.println(" " + (j+1) ); //몇번 반복했는지 확인용
}
```

{: .note }
> 아래처럼 매소드를 활용하면 매인 매소드 코드가 간단해진다

```java
public static void numbering() {  //정의
  for (int i = 0; i < 5; i++) {
  System.out.println(i);
  }
}

public static void main(String[] args) {
  for (int j = 0; j < 5; j++) {
    numbering();  //호출
    System.out.println(" " + (j+1) );
  }
}
```

{: .new-title }
> 🧐
>
> 만약 i를 다른 수로 초기화하고 싶다면? (ex. 1부터 시작)
>
> numbering(**변수**) 활용하기!

---

## 2. 입력과 출력

> 위의 함수를 numbering(**변수**)를 활용하여 표현하자

```java
public static void numbering(int init, int limit) { //복수의 인자
  for (int i = init; i < limit; i++)
    System.out.println(i);
}

public static void main(String[] args) {  
  for (int j = 0; j < 5; j++) {
    numbering(1,5);  //numbering(init, limit)
    System.out.println("  " + (j+1));
  }
}
```


---

## 3. Return
_활용도가 더 높은 출력방법_

{: .note-title }
> Return의 기능
>
> 1. 매소드의 결과를 매인으로 반환
>
> 2. 매소드의 실행을 완전히 종료

>

```java
public static String numbering(int init, int limit) { 
  String output = ""; //빈 문자열 (문자열로 저장하여 리턴하기 위함)
	
  for (int i = init; i < limit; i++)
    output += i;
  return output;  //프린트하지 않고 output에 값을 저장
}

public static void main(String[] args) {
  for (int j = 0; j < 5; j++) {
    String result = numbering(1, 5); //데이터 타입을 지정해줘야함!!
    System.out.println(result);      //output에 저장된 값을 출력함
  }
}
```

{: .important-title }
> Return을 사용할 때
>
> 1. 정의 매소드에서 데이터 타입 바꾸기 
>
> 2. main 매소드에서 호출 시에 데이터 타입 지정하기
>
> (**return 받는 데이터** 기준) _아래 예시 참고_

---

{: .new-title }
> 🤔
>
> 위에서 return은 매소드를 종료시킨다고 했다
>
> 그렇다면 하나의 매소드에서 여러개의 리턴값을 받을 방법이 없을까?
>
> **배열** 사용하기!


> 배열을 사용하여 여러개의 리턴값을 받아보자

```java
import java.util.Arrays;

public class hi {

  public static String[] getKorean() { 
  //1. 정의 매소드에서 배열 타입으로 지정
    String[] korean = {"ga", "na", "da"};
    return korean;
  }
  
  public static void main(String[] args) {
    String[] korean = getKorean(); 
    //2. 매인 매소드에서 배열 타입 지정
    System.out.println(Arrays.toString(korean)); //배열값을 한번에 출력
  }
}
```

```java
[ga, na, da]
```

---

## **이 개념을 왜 배울까?**

{: .highlight }
> 좋은 코드는 유지보수가 필요하다

> 개발자는 개발과정이 힘들더라도 항상 좋은 유지보수를 갖기 위해 노력해야한다
>
> 매소드를 활용하면 변경사항을 적용하거나, 다른 코드에 재활용하기 용이하다
>
> 즉, 유지보수를 높일 수 있는 매소드는 좋은 코드의 키가 될 수 있다 !

---

[Link button](https://opentutorials.org/course/1223/5369){: .btn .btn-outline }