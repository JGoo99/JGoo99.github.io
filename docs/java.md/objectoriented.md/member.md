---
layout: default
title: 멤버
parent: 객체지향프로그래밍
grand_parent: Java
nav_order: 3
---

# III. 멤버

_구성원, 즉 변수와 매소드이다_

---

## 1. 인스턴스의 맴버

> 클래스 아래 n개의 인스턴스를 만들 수 있고
>
> 인스턴스c1과 인스턴스 c2에는 각각의 맴버가 있다


---

## 2. 클래스의 맴버

> 언제 클래스 맴버를 선언하는 것이 좋을까?
>
> 1. 해당 클래스 하의 모든 인스턴스가 공유하는 고정 변수 (ex.π)
>
> 2. 클래스 변수의 변경사항을 모든 인스턴스에 공유해야 할 경우
>
> _아래 예시를 통해 확인해보자_

### i. 클래스의 변수

> 1. 해당 클래스 하의 모든 인스턴스가 공유하는 고정 변수 (ex.π)

```java
class Calculator {
	static double PI = 3.14;
  //사실 final을 이용하여 상수로 선언하는 것이 바람직 (아직 안 배움)
	int left, right;
	
	public void setOprands(int left, int right) {
		this.left = left;
		this.right = right;
	}

//sum과 avg 생략	
	
}

public class test {
	
	public static void main(String[] args) {
		
		Calculator c1 = new Calculator();
		c1.setOprands(10, 20);
		
		Calculator c2 = new Calculator();
		c2.setOprands(20, 40);

		System.out.println(c1.PI);
		System.out.println(c2.PI);
		System.out.println(Calculator.PI); 
    //세개 모두 같은 값이 출력됨
		
	}
}
```

{: .highlight-title }
> class 맴버 접근방법
>
> 객체(c1, c2)를 거쳐서 접근 가능 **c1.PI**
>
> 클래스를 통해 다이랙트로 접근 가능 **Calculator.PI**

---

> 2. 클래스 변수의 변경사항을 모든 인스턴스에 공유해야 할 경우
>
> ex. calculator 결과에 공통적으로 10만큼 더 더하고 싶다면?

```java
class Calculator {
	static double PI = 3.14;
	int left, right;
	static int base = 0;
	
	public void setOprands(int left, int right) {
		this.left = left;
		this.right = right;
	}
	
	public void sum() {
		System.out.println( this.left + this.right + base );
	}
}

public class test {
	
	public static void main(String[] args) {
		
		Calculator c1 = new Calculator();
		c1.setOprands(10, 20);
		c1.sum(); // 10 + 20 + 0
		
		Calculator c2 = new Calculator();
		c2.setOprands(20, 40);
		c2.sum(); // 20 + 40 + 0
		
		Calculator.base = 10;
    //클래스 하의 변수를 변경함
		
		c1.sum(); // 10 + 20 + 10
		c2.sum(); // 20 + 40 + 10
	}
}
```

```java
30
60
40 //변수 변경 이후 10씩 더해진 것을 알 수 있다
70
```

---

### iii. 클래스의 맴버_매소드

> 인스턴스 변수를 사용하지 않고 바로 클래스를 통해 접근하기



```java
class Calculator {
	
	public static void sum(int left, int right) {
		System.out.println( left + right );
	}
  //'static'으로 변경해주어야 함
}

public class test {
	
	public static void main(String[] args) {
		
		Calculator.sum(10, 20);
		Calculator.sum(20, 40);
	}
}
```

{: .warning-title }
> Error
>
> Cannot make a static reference to the non-static method sum(int, int)
>
> from the type Calculator

_sum 매소드에서 static void 로 지정해주어야 에러를 해결할 수 있다_

---


[Link button](https://opentutorials.org/course/1223/5440){: .btn .btn-outline }

