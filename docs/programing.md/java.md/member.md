---
layout: default
title: 멤버
parent: Java
grand_parent: Programing
nav_order: 13
---

# XII. 멤버

_구성원, 즉 변수와 매소드이다_

### **용어 정리**

| Member       | Terms              | 
|:-------------|:-------------------|
| 클래스 매소드   | static method      |
| 클래스 변수     | static field       |
| 인스턴스 매소드  | non-static method  |
| 인스턴스 변수   | non-static field    |

---

## 1. 인스턴스의 멤버

> 클래스 아래 n개의 인스턴스를 만들 수 있고
>
> 인스턴스c1과 인스턴스c2에는 각각의 멤버가 있다

---

## 2. 클래스의 멤버

### i. 클래스의 변수

> 언제 클래스 변수를 선언하는 것이 좋을까?
>
> 1. 인스턴스에 따라서 변하지 않는 값이 필요한 경우 (ex.π)
>
> 2. 값의 변경 사항을 모든 인스턴스가 공유해야 하는 경우
>
> 3. 인스턴스를 생성할 필요가 없는 값을 클래스에 저장하고 싶은 경우
>
> _아래 예시를 통해 확인해보자_

### **i-1) 인스턴스에 따라서 변하지 않는 값이 필요한 경우 (ex.π)**

```java
class Calculator {
  static double PI = 3.14;
  //클래스 고정 변수
  //사실 final을 이용하여 상수로 선언하는 것이 바람직 (아직 안 배움)
  int left, right;
  //인스턴스 변수

  public void setOprands(int left, int right) {
    this.left = left;
    this.right = right;
  }
}

public class test {
	
  public static void main(String[] args) {
		
    Calculator c1 = new Calculator();
    c1.setOprands(10, 20);
		
    Calculator c2 = new Calculator();
    c2.setOprands(20, 40);

    System.out.println(c1.PI);
    System.out.println(c2.PI);
    //모두 같은 값이 출력됨
  }
}
```

{: .highlight }
> 어떤 인스턴스로 접근해도 같은 PI값이 출력된다

---

### **i-2) 값의 변경 사항을 모든 인스턴스가 공유해야 하는 경우**

> ex. calculator 결과에 공통적으로 10만큼 더 더하고 싶다면?

```java
class Calculator {
  int left, right;
  //인스턴스 변수
  static int base = 0;
	//클래스 변수

  public void setOprands(int left, int right) {
    this.left = left;
    this.right = right;
  }
	
  public void sum() {
    System.out.println( this.left + this.right + base );
    //인스턴스 변수 + 클래스 변수
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

{: .highlight }
> 클래스 변수 base의 변경이 모든 인스턴스에 적용되고 있다

---

### **i-3) 인스턴스를 생성할 필요가 없는 값을 클래스에 저장하고 싶은 경우**

_i-1) 예제 참고_

```java
System.out.println(Calculator.PI); 
```

{: .highlight }
> 클래스를 이용해서 클래스 변수에 접근할 수 있기 때문에 인스턴스 생성이 필요없다
>
> 클래스 매소드 또한 인스턴스 없이 접근 가능하다 _아래 예시 참고_

---

### ii. 클래스의 매소드

> 인스턴스를 사용하지 않고 바로 클래스를 통해 매소드 접근하기

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
> Cannot make a **static reference** to the **non-static method** 

_sum 매소드에서 static void 로 지정해주어야 에러를 해결할 수 있다_

{: .highlight }
> 클래스를 통해 클래스 매소드로 접근이 가능하다

---

## 3. 멤버 접근 : 타입별 비교

> 클래스와 인스턴스 멤버에 접근하는 방법을 알아보자

{: .note-title }
> 클래스-인스턴스 접근 원칙
>
> 1. 인스턴스 매소드는 클래스 맴버에 접근 O
>
> 2. 클래스 매소드는 인스턴스 맴버에 접근 X

```java
class C1 {

  static int static_variable = 1;
  //클래스 변수
  int instance_variable = 2;
  //인스턴스 변수
	
  static void static_static() {
    System.out.println(static_variable); 
  //클래스 매소드에서 클래스 변수 접근
  }
	
  static void static_instance() {
    System.out.println(instance_variable); //컴파일 오류
  //클래스 매소드에서 인스턴스 변수 접근
  }
	
  void instance_static() {
    System.out.println(static_variable);
  //인스턴스 매소드에서 클래스 변수 접근
  }
	
  void instance_instance() {
    System.out.println(instance_variable);
  //인스턴스 매소드에서 인스턴스 변수 접근
  }
}
```

```java
public class test {
	
  public static void main(String[] args) {
		
    C1 c = new C1();
  }
}
```

### i. 인스턴스에서 매소드 접근

```java
c.static_static();
```

> 인스턴스를 이용해서 클래스 매소드에 접근 O
>
> 클래스 매소드에서 클래스 변수에 접근 O

```java
c.static_instance();
```

> 인스턴스를 이용하여 클래스 매소드에 접근 O
>
> 클래스 매소드에서 인스턴스 변수에 접근 X

{: .warning-title }
> Error
>
> Cannot make a **static reference** to the **non-static field** 
>
> 클래스(static)매소드에서 인스턴스(non-static) 변수에 접근이 안 된다는 에러

**왜 안 될까?**
<span class="fs-3">
[Link Button](https://wisdom-and-record.tistory.com/35){: .btn }
</span>

1. 클래스와 인스턴스는 만들어지는 시기와 장소가 다르다
2. 클래스가 먼저 생성된 후 인스턴스가 생성된다
3. 즉, 인스턴스의 존재는 클래스 멤버 존재를 보장한다
4. 하지만 클래스의 존재는 인스턴스의 생성을 보장할 수 없다
5. 따라서 클래스 매소드에서 존재가 확실하지 않은 인스턴스 멤버를 호출할 수 없다

```java
c.instance_static();
```

> 인스턴스를 이용해서 인스턴스 매소드에 접근 O
>
> 인스턴스 매소드에서 클래스 변수에 접근 O

```java
c.instance_instance();
```

> 인스턴스를 이용해서 인스턴스 매소드에 접근 O
>
> 인스턴스 매소드에서 인스턴스 변수에 접근 O

### ii. 클래스에서 매소드 접근

```java
C1.static_static();
```

> 클래스를 이용해서 클래스 매소드에 접근 O
>
> 클래스 매소드에서 클래스 변수에 접근 O

```java
C1.static_instance();
```

> 클래스를 이용해서 클래스 매소드에 접근 O
>
> 클래스 매소드에서 인스턴스 변수에 접근 X

{: .warning-title }
> Error
>
> Cannot make a **static reference** to the **non-static field**

```java
C1.instance_static();
```

> 클래스를 이용해서 인스턴스 매소드에 접근 X

{: .warning-title }
> Error
>
> Cannot make a **static reference** to the **non-static method** 

```java
C1.instance_instance();
```

> 클래스를 이용해서 인스턴스 매소드에 접근 X

{: .warning-title }
> Error
>
> Cannot make a **static reference** to the **non-static method**

---

## **이 개념을 왜 배울까?**

{: .highlight }
> 객체지향에 점점 가까워지고 있다!

> 이전 시간까지 클래스와 인스턴스가 무엇인지 배웠다면
>
> 이번엔 그것들이 어떤 것들로 이루어져있고, 어떻게 만들어지는지 배운다
>
> 다음엔 각 멤버의 소속을 배우고, 접근 범위를 배운다

---

[Link button](https://opentutorials.org/course/1223/5440){: .btn .btn-outline }

