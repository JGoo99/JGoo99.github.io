---
layout: default
title: 조건문
parent: Java
nav_order: 5
---

# IV. 조건문

## 1. if

```java
String id = args[0];
if (id.equals("Goo")) {
	System.out.println("로그인 완료");
} else {
	System.out.println("잘못된 ID");
}
```
_문자열 비교 연산자로 아이디 입력값이 맞는지 출력하는 조건문_

{: .warning-title }
>Error
>
> args[0]에 입력 받은 값이 없기 때문에 아래와 같은 에러 발생

<div class="code-example" markdown="1">
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException:
Index 0 out of bounds for length 0 at DynamicBeat dynamic_beat_1.hi.main(hi.java:6)
</div>

### **해결방법**
> Run - run configurations - arguments - variables - string_prompt

{: .new }
> 만약 비밀번호까지 입력받는 로직을 만들고 싶다면?
>
> **조건문의 중첩**

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

## 2. else
## 3. else if
## 4. switch


[Link button](https://opentutorials.org/course/1223/5335){: .btn .btn-outline }