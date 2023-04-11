---
layout: default
title: 배열
parent: Java
grand_parent: Programing
nav_order: 7
---

# VII. 배열
_연관된 정보를 그룹핑하는 역할_

> 배열에 사용되는 단어들의 정의 먼저 알고가자

| ga   | na   | da   | ra   |
|:-----|:-----|:-----|:-----|
| 0    | 1    | 2    | 3    |

* 횡의 개수 = length(배열이 담을 수 있는 크기)
* ga, na, da, ra = element(원소)
* 0, 1, 2, 3 = index(식별자)


---

## 1. 변수와 상수

<div class="code-example" markdown="1">
예를 들어
선생님이 교실에 들어가 '반장 나와봐' 라고 했을 때
반장이 누구인지는 몰라도 한 명 나옴.
그 반장이 전학을 간다해도 선생님이 '반장 나와봐'라고 한다면
새로운 반장이 나옴.
</div>
```markdown
반장=변수 / 교실=프로그램 / 학생들=상수
```

---

## 2. 배열의 사용

### i. 한번에 정의하는 방법

```java
String[] korean = {"ga", "na", "da", "ra"};

System.out.println(korean[0]);
System.out.println(korean[3]);
```

```java
ga
ra
```

### ii. 하나씩 정의하는 방법

```java
String[] korean = new String[4];
korean[0] = "ga";
korean[1] = "na";
korean[2] = "da";
korean[3] = "ra";

System.out.println(korean.length);
System.out.println(korean[3]);
```

```java
4
ra
```

---

## 3. 배열과 반복문

> 배열을 활용하여 동물의 건강검진 확인 문구를 출력해보자
>
> 배열 지정 후 for문을 활용하기

```java
String[] animals = {"dog", "cat", "rat"};

for (int i = 0; i < animals.length; i++) {
  String animal = animals[i];
  System.out.println(animal + " 검사완료.");
}
```

{: .note-title }
> for each
>
> '배열+반복문'을 체계화한 문법이 있다!

```java
String[] animals = {"dog", "cat", "rat"};
		
for (String e : animals)
  System.out.println(e + " 검사완료.");
```

---

## 4. 배열의 오류와 한계

### i. 배열의 오류
_배열의 크기보다 큰 index를 호출했을 때_

```java
String[] korean = {"ga", "na", "da"};

System.out.println(korean[3]);
```

{: .warning-title }
>Error
>
>Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException:
>
>Index 3 out of bounds for length 3
>
>at DynamicBeat/dynamic_beat_1.hi.main(hi.java:8)
```

> 아래의 경우도 같은 오류를 발생시킨다

```java
String[] korean = new String[3];
korean[0] = "ga";
korean[1] = "ga";
korean[2] = "ga";
```

### ii. 배열의 한계

_배열은 초기화할 때 그 크기가 정해진다._
_그 크기를 미리 예측하고 변수를 집어넣기는 어렵다._

> Collection 기능을 사용하면 배열을 유용하게 사용가능
>
> 객체지향 이후 정리함!!

---



[Link button](https://opentutorials.org/course/1223/5373){: .btn .btn-outline }