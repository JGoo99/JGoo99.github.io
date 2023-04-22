---
layout: default
title: 프로젝트 환경설정
parent: Spring
grand_parent: Programing
nav_order: 2
---

# I. 프로젝트 환경설정

---

## 1. 프로젝트 생성

0. H2 데이터베이스 다운로드

> 아래 사이트에 자세하게 설명되어 있다

https://so-easy-coding.tistory.com/5

{:style="counter-reset:none"}
1. 스프링 부트 사이트 이동

https://start.spring.io/ 

[Link button](https://opentutorials.org/course/1223/5261){: .btn .btn-outline }

{:style="counter-reset:none"}
2. 프로젝트 선택

![preference1](https://user-images.githubusercontent.com/126454114/233755520-ad4cdb4a-ea76-4aed-a435-27bf77d47154.jpg)

![preference2](https://user-images.githubusercontent.com/126454114/233755760-12d8e7b9-a9e3-4ac1-86bf-a2f3894a66ef.jpg)

{: .important-title }
> 스프링부트 버전
>
> 3.0 이상을 선택했기 때문에 자바 17 이상을 사용해야 한다
>
> 현재 자바 11을 사용하고 있기 때문에 바꿔주어야 한다

<br/>

- 자바 버전을 17로 바꿔준 모습

![preference3](https://user-images.githubusercontent.com/126454114/233755589-7fee3330-61bc-478e-a740-7906feb1eee4.jpg)


<br/>

{:style="counter-reset:none"}
3. 라이브러리 살펴보기

> 프로젝트 생성 시 라이브러리를 선택할 수 있다
>
> 아래는 선택항목이다

![preference4](https://user-images.githubusercontent.com/126454114/233756546-1795dc9d-4e5b-417f-81cb-75cb6bca3f7b.jpg)

<br/>

- Spring Web

> 웹 프로젝트를 만들 것이기 때문이다

- Thymeleaf

> html을 만들어주는 템플릿 엔진이 필요하다
>
> 템플릿 종류는 다양하지만 깔끔한게 아직 없음 _뒤에서 더 설명_

<br/>

{:style="counter-reset:step-counter 3"}
4. 스프링 생성

> 이후 **generate**를 눌러 프로젝트를 생성한 후
>
> home에 새로운 디렉토리를 만들어 압축을 풀어준다

<br/>

{:style="counter-reset:none"}
5. intellij에서 열기  

open - (study-hello_spring-build.gradle) - open as project
{: .fs-5 .ls-10 .text-mono .code-example }

{: .new-title }
> test 코드
>
> src 안에 main과 test 파일이 이미 나눠져있는 것을 볼 수 있다
>
> 요즘 트렌드에 test 코드가 점점 중요해지고 있다는 사실을 알 수 있다

<br/>

{:style="counter-reset:none"}
6. build.gradle 살펴보기

### i. build.gradle

> 버전설정 및 라이브러리 가져오는 역할

```java
plugins {
	id 'java'
	id 'org.springframework.boot' version '3.0.6'
	id 'io.spring.dependency-management' version '1.1.0'
}
//이 부분은 나중에 공부하는 것이 좋다
//지금은 버전설정하고 라이브러리를 땡겨오는구나 정도만 파악하기

group = 'hello'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '17' //java version: 17

repositories {
	mavenCentral()
}
//아래의 라이브러리를 mavenCentral에서 다운받도록 설정됨
//필요 시 특정 사이트 url을 넣을 수 있음

dependencies {
	implementation 'org.springframework.boot:spring-boot-starter-thymeleaf'
	implementation 'org.springframework.boot:spring-boot-starter-web'
  //라이브러리 선택했던 것 두개 (spring web, thymeleaf)
	testImplementation 'org.springframework.boot:spring-boot-starter-test'
  //요즘은 테스트 라이브러리가 기본적으로 들어감(참고)
}

tasks.named('test') {
	useJUnitPlatform()
}
```

<br/>

{:style="counter-reset:none"}
7. 매인매소드 실행

> 매인 매소드를 실행했더니 아래와 같은 결과가 나왔다

{: .warning-title }
> Error
>
> Related gradle configuration was not found.
>
> "Please, re-import the Gradle project and try again.

> 아직 intellij에 익숙하지 않았던 탓에 gradle의 새로고침 버튼 조차 몰랐다
>
> **.gradle 파일로 가서 새로고침**을 해주었더니 다운로드가 시작되었고, 매인매소드도 정상 작동했다

<br/>

> 매인 매소드가 정상 작동되어 콘솔창에 긴 글이 출력되었다
>
> 그 중 아래에서 두번째 줄의 내용이다

```
main] o.s.b.w.embedded.tomcat.TomcatWebServer  :
Tomcat started on port(s): 8080 (http) with context path ''
```

<br/>

{:style="counter-reset:none"}
8. 중간 점검

```
http:localhost:8080
```

> 위 링크를 입력하여 404 페이지가 뜨는지 확인한다
>
> 아직 아무것도 만든 것이 없기 때문에 404 에러 페이지가 뜬다면 지금까지 잘 온 것이다

_404 에러페이지가 뜬 모습_

![preference5](https://user-images.githubusercontent.com/126454114/233772770-553a1259-58ac-468a-a9aa-284724e04d5d.jpg)

<br/>

{: .highlight }
> intellij의 실행을 중단하고 404페이지를 새로고침하면 **사이트에 연결할 수 없음** 메시지가 뜬다

---

## 2. View 환경설정



---

## 3. 빌드하고 실행하기



---

## **이 개념을 왜 배울까?**

{: .highlight }
> 

> 

---

[Link button](https://opentutorials.org/course/1223/5261){: .btn .btn-outline }