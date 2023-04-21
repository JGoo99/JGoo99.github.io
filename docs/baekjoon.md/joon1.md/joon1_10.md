---
layout: default
title: 곱셈
parent: 입출력과 사칙연산
grand_parent: 백준 문제풀이
nav_order: 11
---

# 입출력과 사칙연산

---

## #문제_2588

> (1)과 (2)위치에 들어갈 세 자리 자연수가 주어질 때 (3), (4), (5), (6)위치에 들어갈 값을 구하는 프로그램을 작성하시오.

![joon1_10](https://user-images.githubusercontent.com/126454114/233568872-fdc8404c-0114-47c4-9bfa-5f806c18bd6e.jpg)


---

### #입력

> 472
>
> 385

### #출력

> 2360
>
> 3776
>
> 1416
>
> 181720


### #알고리즘 분류

> 수학, 사칙연산

---

### #풀이

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
	  
    Scanner i = new Scanner(System.in);
    int A = i.nextInt();
    int B = i.nextInt();
	  
    int a = A * (B%10);         //472 * 5
    int b = A * (B%100 - B%10); //472 * (85 - 5)
    int c = A * (B - B%100);    //472 * (385 - 85)
	 
    System.out.println( a );
    System.out.println( b/10 );
    //전체값을 구할 땐 그대로 사용해도 되지만, 출력값에서는 일의자리수 생략
    System.out.println( c/100 );
    //위와 같은 맥락
    System.out.println( a+b+c );
  }
}
```

---

### #유의할 점

{: .highlight }
> 유지보수가 좋은 코드에 대한 고민

> 솔직히 입력받는 숫자가 주어진 문제이기 때문에 10으로 나누는 번거로움보다
>
> 그냥 -5, -85를 하면 아주 쉽게 원하는 출력값을 낼 수 있다
>
> 하지만 입력값이 바뀐다면 내가 작성한 코드는 쓸모없는 함수가 된다
>
> 따라서 입력값이 바뀌었을 때도 사용할 수 있는 코드에 대해 고민을 했다

