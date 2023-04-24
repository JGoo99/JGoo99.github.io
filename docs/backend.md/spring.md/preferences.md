---
layout: default
title: 프로젝트 환경설정
parent: Spring 입문
grand_parent: Back-end
nav_order: 2
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

# I. 프로젝트 환경설정
{: .no_toc }

---

## 1. 프로젝트 생성

1. H2 데이터베이스 다운로드

> 링크 사이트에 자세하게 설명되어 있다
[Link button](https://so-easy-coding.tistory.com/5){: .btn .btn-outline }

<br/>

{:style="counter-reset:none"}
2. 스프링 부트 사이트 이동

https://start.spring.io/ 

[Link button](https://opentutorials.org/course/1223/5261){: .btn .btn-outline }

<br/>

{:style="counter-reset:none"}
3. 프로젝트 선택

![preference1](https://user-images.githubusercontent.com/126454114/233755520-ad4cdb4a-ea76-4aed-a435-27bf77d47154.jpg)

![preference2](https://user-images.githubusercontent.com/126454114/233755760-12d8e7b9-a9e3-4ac1-86bf-a2f3894a66ef.jpg)

{: .important-title }
> 스프링부트 버전
>
> 스프링부트 3.0 이상을 선택했기 때문에 자바 17 이상을 사용해야 한다
>
> 현재 자바 11을 사용하고 있기 때문에 바꿔주었다

<br/>

- 자바 버전을 17로 바꿔준 모습

![preference3](https://user-images.githubusercontent.com/126454114/233755589-7fee3330-61bc-478e-a740-7906feb1eee4.jpg)


<br/>

{:style="counter-reset:none"}
4. 라이브러리 살펴보기

> 프로젝트 생성 시 라이브러리를 선택할 수 있다
>
> 아래는 선택된 항목이다

![preference4](https://user-images.githubusercontent.com/126454114/233756546-1795dc9d-4e5b-417f-81cb-75cb6bca3f7b.jpg)

- **Spring Web**

> 웹 프로젝트를 만들 것이기 때문에 가져온다

- **Thymeleaf**

> html을 만들어주는 템플릿 엔진이 필요하다
>
> 템플릿 종류는 다양하지만 깔끔한게 아직 없음 _뒤에서 더 설명_

<br/>

{:style="counter-reset:none"}
5. 스프링 생성

> 이후 **generate**를 눌러 프로젝트를 생성한 후
>
> home에 새로운 디렉토리를 만들어 압축을 풀어준다

<br/>

{:style="counter-reset:none"}
6. intellij에서 열기  

open - (study-hello_spring-build.gradle) - open as project
{: .fs-3 .ls-10 .text-mono .code-example }

{: .new-title }
> test 코드
>
> src 안에 main과 test 파일이 이미 나눠져있는 것을 볼 수 있다
>
> 요즘 트렌드에 test 코드가 점점 중요해지고 있다는 사실을 알 수 있다

<br/>

> 프로젝트를 열었으면 **build.gradle**를 살펴보자
>
> 해당 그래들은 버전설정 및 라이브러리 가져오는 역할을 한다

```groovy
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

{: .highlight }
> intellij의 실행을 중단하고 404페이지를 새로고침하면 **사이트에 연결할 수 없음** 메시지가 뜬다

---

## 2. 라이브러리 살펴보기

<br/>

1. 다운 받은 라이브러리와 실제 라이브러리 차이

> **External Libraries** : 땡겨온 라이브러리
>
> 다운 받은 라이브러리에 비해 실제 라이브러리의 양이 많다
>
> 땡긴 적이 없는 수많은 라이브러리들 존재하는 이유는 **의존관계** 때문이다
>
> 아래를 보면 라이브러리 간 의존관계의 중첩을 볼 수 있다

_cmd+cmd 후 오른쪽 상단 gradle 클릭_

![preference7](https://user-images.githubusercontent.com/126454114/233788866-5c715679-e6fa-48d0-bc29-f763ccba088c.jpg)

> 확장 화살표가 없고, (*) 표시된 라이브러리는 중복처리된 것이다

<br/>

- intellij 꿀팁

![preference6](https://user-images.githubusercontent.com/126454114/233788374-06ff9dfb-f96b-48f5-8176-c94f26573a6e.jpg)

{: .note-title }
> 파일 검색 기능
>
> 파일을 검색하고싶을 때 파일 하나 선택 후 키보드로 바로 입력하여 검색 가능

<br/>

> 아래 사진을 보면 spring-core가 의존관계이기 때문에 자동으로 땡겨지고있다
>
> 이처럼 spring boot와 관련된 라이브러리를 쓰면 spring core까지 다 땡겨서 저절로 세팅된다

![preference8](https://user-images.githubusercontent.com/126454114/233789458-cbeb75c0-27b8-4555-90b1-4ea46b6a2ad2.jpg)

---

## +) 로그와 관련된 간단한 언급
{: .no_toc }

{: .highlight }
> 현업에선 **System.out.println();** 사용을 안 한다?

> 실무에선 **log**로 받는 경우가 많아서 syso을 거의 사용하지 않는다

<br/>

- 로그에 관련된 라이브러리가 스프링부트와 함께 자동으로 당겨진 모습

![preference9](https://user-images.githubusercontent.com/126454114/233790929-c8528f97-6e91-404d-85bd-dd0f211864fe.jpg)

{: .new-title }
> **logback** 과 **slf4j**
>
> 로그를 어떤 구현체로 출력할 것인가?
>
> 요즘 트랜드는 logback이고(성능/속도 측면에서 우세), slf4j는 인터페이스이다

---

## 3. View 환경설정

> 이전 수업까지는 404 에러 페이지 띄우기까지 했었다
>
> 이번 수업에서는 페이지를 제작해서 페이지를 띄워보자

### i. Welcome Page 만들기
{: .no_toc }

> 도매인만 누르고 들어왔을 때 뜨는 첫 화면으로. 가장 간단한 페이지 제작이다

<br/>

1. Welcome Page 만들기

> 아래 사진의 경로에 html을 만든 뒤 간단한 코드를 작성한다

![preference10](https://user-images.githubusercontent.com/126454114/233822135-fcf97fd2-f832-4ce8-9468-deb27e3efa74.jpg) 

> html 파일은 static 코드를 그냥 넘겨주는 것이다

<br/>

> 또한, spring.io에서는 검색하여 정보를 얻을 수 있다
>
> 아래 경로로 들어가 'welcome page'를 찾는다

```
https://docs.spring.io/spring-boot/docs/current/reference/html/web.html#web.servlet.spring-mvc.welcome-page
```

> 해당 내용은 아래와 같다

<div class="code-example" markdown="1">
1.1.5. Welcome Page
Spring Boot supports both static and templated welcome pages. It first looks for an index.html file in the configured static content locations. If one is not found, it then looks for an index template. If either is found, it is automatically used as the welcome page of the application.
</div>
```markdown
index.html 파일을 찾는 순서를 설명한 글이다
```

<br/>

### ii. 템플릿으로 화면 구성해보기
{: .no_toc }

> 템플릿 엔진을 활용하면 위의 html의 파일 코드를 수정하여 원하는대로 모양을 바꿀 수 있다

<br/>

1. 컨트롤러 클래스 생성하기

> src/main/java/hello.hellospring에 **controller 패키지 생성** 후 
>
> hellocontroller 클래스 생성한다 코드는 아래와 같다

_hellocontroller.class_

```java
package hello.hellospring.controller;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class HelloController {

  @GetMapping("hello") //맵 어플에서
  public String hello (Model model) {
		
    model.addAttribute("data", "hello!!");
    //(attributeName: "data", attributeValue: "hello!!")
    return "hello";
  }
}
```

<br/>

2. html 파일 생성하기

> src/main/resources/templates에 hello.html 생성 후 아래와 같이 작성한다

```html
<!DOCTYPE HTML>
<html xmlns:th="http://www.thymeleaf.org">
<head>
  <title>Hello</title>
  <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
</head>
<body>
<p th:text="'안녕하세요. ' + ${data}" >안녕하세요. 손님</p>
<!--&{data}는 Hellospring클래스의 attributeValue값과 치환된다-->
</body>
</html>
```

{: .highlight}
> HTML 주석처리
>
> <!--내용 작성-->

<br/>

3. 실행해보기

> intellij에서 재실행 후 검색창에 아래 링크를 작성하여 들어가면 아래 화면이 출력된다
>
> **_localhost8080/hello_**

![preference11](https://user-images.githubusercontent.com/126454114/233960208-37649383-138d-43ed-ae83-27b2ec01a518.jpg)

<br/>

4. 동작 과정

![preference12](https://user-images.githubusercontent.com/126454114/233962124-75e5e9a8-8c53-4cec-a48c-1380b50cc428.jpg)

- 검색창에 localhost8080/**hello** 입력

> 스프링 부트는 **톰캣**이라는 웹서버를 내장하고 있음
>
> 이 웹서버에 위 url이 들어오고 "hello" 값과 매칭값이 있는지 spring에서 찾음

- hello 매소드 실행

```java
public String hello (Model model) {
  model.addAttribute("data", "hello!!");
  return "hello";
}
```

> 모델에 키는 data, 값은 hello!!를 대입한 후 hello를 리턴한다

- 템플릿 엔진 처리

> hello를 리턴하면 뷰 리졸버가 resources:templates의 hello.html을 찾아 랜더링한다
>
> resources:templates/**hello**.html

---

## 4. 빌드하고 실행하기

> 터미널에 들어가서 빌드하고 실행해보자

![preference13](https://user-images.githubusercontent.com/126454114/233966526-953324e9-6f7f-49cf-ab66-a33c11a57521.jpg)

![preference14](https://user-images.githubusercontent.com/126454114/233966958-86052d3d-6907-48d6-99d7-e3e0ef8d72a9.jpg)

> 이후 localhost8080, localhost8080/hello를 확인해보면 똑같이 실행된다

---

## **이번 수업 정리**

{: .highlight }
> 스프링 개념을 이해하기 위한 간단한 실습

> 프로젝트를 생성해보고 템플릿을 활용하여 실제 화면을 띄워보는 과정을 통해
>
> 라이브러리에는 무엇이 있으며 화면을 띄우는 과정에서 어떤 파일들이 필요한 지 알아보았다
