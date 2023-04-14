---
layout: default
title: 오버라이딩
parent: Java
grand_parent: Programing
nav_order: 18
---

# XVII. 오버라이딩

---

## 1. 정의

> 상위 클래스에서 상속받은 매소드를 새롭게 재정의한다

---

## 2. 사용법

> 상위 클래스에 같은 매소드 명으로 재정의하면 하위클래스의 매소드로 호출된다

```java
class Cal{
  //생성자 생략	
  public void sum() {
    System.out.println( this.left + this.right );
  }
}

class diviCal extends Cal {
  //생성자 생략	
  public void sum() {
    System.out.println( "결과는 " + (this.left + this.right) + "입니다");
  }
	
public class test {
	
  public static void main(String[] args) {
		
    diviCal c1 = new diviCal(20, 10);
    c1.sum();
  }
}
```

```java
결과는 30입니다
```
---

## **이 개념을 왜 배울까?**

{: .highlight }
> 

> 
>
> 
>
>  

---

[Link button](https://opentutorials.org/course/1223/6090){: .btn .btn-outline }
