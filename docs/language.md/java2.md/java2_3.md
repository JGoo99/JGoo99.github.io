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

### i. if 문
{: .no_toc }

- **if 문의 구조**

> if 문은 조건식과 괄호로 이루어져있다
>
> if문의 조건식이 true면 괄호 안의 문장을 수행하라는 의미의 문법이다

```java
if (조건식) {
  괄호 안의 문장
}
```

{:style="counter-reset:none"}
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

### iii. if-else if 문
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

### iv. 중첩 if 문
{: .no_toc }

> if 문 안에 if 문을 포함시키는 문법으로, 중첩 횟수에는 제한이 거의 없다

```java
if (조건식 1) {
  조건식 1이 참일 경우 수행
  if (조건식 2) {
    조건식 1과 2가 모두 참일 경우 수행
  }
}
```

<br/><br/>

### v. switch 문
{: .no_toc }


<br/><br/>

---

## 반복문

### i. for 문
{: .no_toc }


<br/><br/>

### ii. while 문
{: .no_toc }


<br/><br/>

### iii. do-while 문
{: .no_toc }


<br/><br/>

### iv. break 문
{: .no_toc }


<br/><br/>

### v. continue 문
{: .no_toc }


<br/><br/>

### vi. 이름 붙은 반복문
{: .no_toc }
