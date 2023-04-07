---
layout: default
title: 조건문
parent: Java
nav_order: 5
---

# V. 조건문

## 1. if

> 문자열 비교 로직을 활용하여 로그인 로직을 만들어보자

```java
String id = args[0];
if (id.equals("Goo")) {
  System.out.println("로그인 완료");
} 
```

### 결과

<div class="code-example" markdown="1">
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException:
Index 0 out of bounds for length 0 at DynamicBeat dynamic_beat_1.hi.main(hi.java:6)
</div>

{: .warning-title }
> Error
> 
> args[0]에 입력 받은 값이 없기 때문에 위와 같은 에러 발생

> 해결방법
>
> Run - run configurations - arguments - variables - string_prompt

---

## 2. else

> else를 이용해서 아이디가 맞았는지 틀렸는지 나타내는 로직을 만들어보자

```java
String id = args[0];
if (id.equals("Goo")) {
  System.out.println("로그인 완료");
} else {
  System.out.println("잘못된 ID");
}
```
---

{: .new-title }
> 💡
>
> 만약 비밀번호까지 입력받는 로직을 만들고 싶다면?
>
> **조건문을 중첩하여 사용하기**

### if 조건문의 중첩

```java
String id = args[0];
String password = args[1];
if (id.equals("Goo")) {
  if (password.equals("1111")) {
	  System.out.println("로그인 완료");
  } else {
	  System.out.println("비밀번호 오류");
  }
} else {
    system.out.println("로그인 완료");
}
```

---

## 3. else if
_조건문을 더 자유롭게 사용하기 위함_

```java
import java.util.Scanner;

public class hi {

  public static void main(String[] args) {
    int age;

	Scanner sc = new Scanner(System.in);
	System.out.println("나이?")
	age = sc.nextInt(); 
	//위의 내용은 직접 입력값을 받기 위한 로직

	if (age > 10) {
		System.out.println("입장가능"); //10살 초과
	} else if (age == 10) {			  //10살 이하
		System.out.println("이벤트당첨");//딱 10살
	} else {
		System.out.println("입장불가");  //10살 미만
	}

}
```

---

## 4. switch

_사용빈도는 적으나 조건 구문이 많다면 더 명료하게 표현 가능_
_또한 조건에 들어갈 수 있는 데이터 타입이 한정적임_

```java
switch(1) {
case 1 :
  System.out.println("one");
  break;
case 2 : 
  System.out.println("twe");
  break;
case 3 : 
  System.out.println("three");
  break;
default:
  System.out.println("default");
}
```
### if문으로 대체 가능함

```java
int val = 1;
if (val == 1) {
  System.out.println("one");
} else if (val == 2) {
	System.out.println("twe");
} else if (val == 3) {
 	System.out.println("three");
} else {
    System.out.println("default");
}
```

---

[Link button](https://opentutorials.org/course/1223/5335){: .btn .btn-outline }