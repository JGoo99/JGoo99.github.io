---
layout: default
title: 연산자
parent: Java
nav_order: 4
---

# IV. 연산자 

---

## 1. 산술 연산자

| 연산자   | 의미    |
|:-------|:-------|
| +      | 더하기   |
| -      | 빼기    |
| *      | 곱하기   |
| /      | 나누기   |
| -      | 나머지   |

_연산자 중에 +는 문자열에도 사용 가능하다_
```java
String a = "안녕";
String b = "하세요";
System.out.println(a + b);
```
```markdown
안녕하세요
```

---

## 2. 단항 연산자
_하나의 항을 대상을 이루어지는 연산자_

| 연산자   | 의미       |
|:-------|:----------|
| +      | 양수(사용x) |
| -      | 음수       |
| ++     | 1씩 증가   |
| --     | 1씩 감소   |

```java
int i = 3;
i++			// i=i+1
System.out.println(i);    // 4
++i;
System.out.println(i);    // 5
System.out.println(++i);  // 6
System.out.println(i++);  // 6 i++는 print가 끝나고 더해지는 특징이 있음
System.out.println(i);    // 7
```

---

## 3. 비교 연산자

| 연산자    | 의미       |
|:--------|:----------|
| ==      | 같다       |
| !=      | 같지 않다   |
| >       | 크다       |
| >=      | 크거나 같다  |
| .equals | 같다(문자열) |

_문자열 비교 예시_
```java
String a = "Hello world";
String b = new String("Hello world");

System.out.println(a == b);
System.out.println(a.equals(b));
```

```java
false
true
```

---

## 4. 논리 연산자

| 연산자    | 의미       |
|:--------|:----------|
| &&      | and       |
| 아래 참고 | or        |
| !       | not       |

### i. && (and)

> ID와 PASSWORD가 모두 맞아야 하는 로그인 로직을 만들어보자

```java
String id = args[0];
String password = args[1];
		
if (id.equals("Goo") && password.equals("111")) {
  System.out.println("login");
} else {
  System.out.println("worng");
}
```

### ii. || (or)

> ID가 둘 중 하나라도 맞으면 되는 로그인 로직을 만들어보자

```java
String id = args[0];
		
if (id.equals("Goo") || id.equals("goo")) {
  System.out.println("login");
} else {
  System.out.println("worng");
}
```

### iii. ! (not)

```java
if (!true) {
  System.out.println(1);
}
if (!false) {
  System.out.println(2);
}
```

```java
2
```


---



[Link button](https://opentutorials.org/course/1223/5331){: .btn .btn-outline }