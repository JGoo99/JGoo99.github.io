---
layout: default
title: 반복문
parent: Java
nav_order: 6
---

# VI. 반복문

---

## 1. while

> i(int)를 이용하여 d+day를 만들어보자 (ex. 4일 까지)

```java
int i = 1;
		
while (i < 5) {
  System.out.println( "D + " + i );
  i++;
}
```

```java
D + 1
D + 2
D + 3
D + 4
```

{: .highlight-title }
> 🧐
>
> i++를 syso 위에 넣으면 어떻게 될까?

```java
D + 2 // (i = 1) 에서 (i+1 = 2) 가 된 상태로 출력
D + 3
D + 4
D + 5 // (i = 4) 에서 (i+1 = 5) 가 된 상태로 출력
```

{: .highlight }
> 1일 부터 시작이 안 되니까 위에 넣으면 안 되겠다..!ㅎ

---

## 2. for
_자주 사용하는 로직 (ex. while) 을 하나의 문법으로 체계화한 것_

> 위에서 만들었던 로직을 for를 활용하여 만들어보자

```java
for (int i = 1; i < 5; i++) {
  System.out.println( "D + " + i );
}
```

```
결과는 동일하며 코드가 더욱 간단해짐을 알 수 있음
```
---

## 3. break
_반복문의 중단_

> 최대 수용 정원이 3명인 앨리베이터를 가정하고
> ~~(한 명 씩 무조건 탑승 가정,,ㅎ)~~
>
> 수용 가능 인원과 만원되었음을 알리는 로직을 만들어보자

```java
for (int i = 0; i < 6; i++) {  //6은 3보다 큰 숫자로 임의 지정
  if (i == 3) {
	  System.out.println("만원되었습니다.");
	  break;
  }
  System.out.println("현재 수용 인원: " + (3-i));
}
```

---

## 4. continue
_직후 문장의 명령을 수행하지 않음. (반복문 자체의 중단이 아님)_

{: .new-title }
> 💡
>
> 만약 인원 초과로 인해 고장 문구를 출력하고 싶다면?
>
> **continue**를 활용해보자 ~~(더 쉬운 방법 있을지도? 걍 지어냄~)~~

```java
for (int i = 0; i < 5; i++) {
  if (i == 3) {
	  System.out.println("만원되었습니다.");
	  continue;
  }
  if (i > 3) {
	  System.out.println("고장.");
	  continue;
  }
  System.out.println("현재 수용 인원: " + (3-i));
}
```

---

### **반복문의 중첩**

> 00~99까지 출력하는 로직을 만들어보자

```java
for (int i = 0; i < 10; i++) {
  for (int j = 0; j < 10; j++) {
	  System.out.println(i + "" + j);
  }
}
```

{: .highlight-title }
> 🧐
>
> 비효율적인(?) 0을 없애려면 어떻게해야할까?
>
> **반복문+조건문** 사용하기!

```java
for (int i = 0; i < 10; i++) {
  for (int j = 0; j < 10; j++) {
	  if (i == 0) {
	    if (j == 0)
		    continue;
	    System.out.println(" " + j);
	    continue;
	  }
	  System.out.println(i + "" + j);
  }
}
```
~~근데 이게 더 비효율적인듯ㅋㅋ~~


---

[Link button](https://opentutorials.org/course/1223/5366){: .btn .btn-outline }