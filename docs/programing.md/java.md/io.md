---
layout: default
title: 입력과 출력
parent: Java
grand_parent: Programing
nav_order: 10
---

# IX. 입력과 출력

_입력 : 키보드, 마우스, 터치 등의 자극_
_출력 : 그에 대한 반응_

---
## 0. **String[] args**
_입출력을 알아보기 전, 자주 보았던 이 문구가 무엇인지 알아보자_

```java
public class hi {
	
  public static void main(String[] args) {
    System.out.println(args.length); 
    // hi 어플리케이션 안에 전달한 입력값의 수
  }
}
```

```java
0
```

**정의**

| 단어          | 의미                            |
|:-------------|:-------------------------------|
| String[]     | 배열을 담을 수 있는 데이터 타입       |
| main         | 매소드 중 하나                    |
| void         | 매인 매소드의 출력값이 존재하지 않는다  |
| 파라미터       | 매소드 들어오는 입력값               | 

> 즉, 배열 **args**를 파라미터로 입력받는 **main** 매소드
>
> 때문에, args.length는 배열 args의 입력값 크기를 나타내는 것임

---

## 1. arguments 설정 활용

> 이클립스에서 args에 입력 후 출력해보자

```java
public static void main(String[] args) {
  for (String e : args) {       
  //run Configuration - arguments - ${string_prompt} 추가
    System.out.println(e);
  }
}
```

```java
one   //입력창에 'one two' 입력시
two
```

---

## 2. Scanner 활용

### i. 콘솔창에서 입력

```java
import java.util.Scanner;

public class inputDemo1 {

  public static void main(String[] args) {

    Scanner sc = new Scanner(System.in);
    //system.in : 사용자가 입력한 값
    //그 값을 Scanner()가 읽어서 sc에 저장

    int i = sc.nextInt();
    //사용자가 입력한 후 Enter를 치면 i에 저장됨

    System.out.println(i*1000);
    sc.close();
  }
}
```

{: .note-title }
> 정의
>
> **import java.util.Scanner;**
>
> 의미 : java util 안에 있는 Scanner Library를 사용하겠다
>
> _scanner 또한 객체에 대한 이해가 필요함_

---

{: .new-title }
> 🧐
>
> 위에서는 한번의 io로 끝났는데, 계속 io를 하고싶다면?
>
> Scanner + **while** 활용하기

```java
Scanner sc = new Scanner(System.in);

while (sc.hasNextInt()) {
//sc.hasNextInt가 Int의 데이터타입(정수)이라면 true가 됨
//정수가 아닌 데이터타입을 입력하면 scanner는 종료됨

  System.out.println(sc.nextInt() * 1000);
}
sc.close();
```

---

### ii. file 데이터 입력

#### **먼저 iterm으로 txt 만들기**

```
cat > memo.txt
//생성 (최상위 폴더에 만들어야함_javaProjectFile)

내용 작성
ctrl + d

vi memo.txt //편집

rm memo.txt //삭제
```

```java
try {
  File file = new File("memo.txt");
  Scanner sc = new Scanner(file);
  while (sc.hasNextInt()) {
    System.out.println(sc.nextInt() * 1000);
  }
  sc.close();
} catch (FileNotFoundException e) {
  e.printStackTrace();
}
```

{: .important-title }
> 🐷
>
> 키보드로 직접 입력하는 것만이 입력이 아니라
>
> 입(출)력을 **광범위**한 의미로 인지하자 !

---

## 3. GUI
_Graphic User Interface_

> CLI (Command Line Interface)
>
> 명령어 기반 인터페이스 (ex. Terminal) 의 대칭점

---

## **이 개념을 왜 배울까?**

{: .highlight }
> 입력과 출력에 대한 광범위한 이해가 필요하다

> 키보드, 클릭 등이 입력의 전부가 아니며,
>
> 눈에 보이는 변화만이 출력의 전부가 아니다
>
> 파일을 읽어오고, 안 보이는 곳에 데이터들을 저장하는 것들도 모두 입출력이 될 수 있다

---

지금까지 **절차지향** 프로그래밍이었음

앞으로 **객체지향** 에 대한 긴 학습시간이 필요함!!

---

[Link button](https://opentutorials.org/course/1223/5575){: .btn .btn-outline }