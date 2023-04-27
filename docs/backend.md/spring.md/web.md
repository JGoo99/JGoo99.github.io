---
layout: default
title: 웹개발 기초
parent: Spring 입문
grand_parent: Back-end
nav_order: 3
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

# II. 웹개발 기초
{: .no_toc }

> 웹개발에는 크게 3가지 방식이 있다 : 정적컨텐츠, MVC와 템플릿엔진, API
>
> **정적콘텐츠** : html파일만을 이용하여 그대로 보내는 것
>
> **동적콘텐츠** : 서버의 조작을 통해 컨텐츠 내용을 바꿔 출력하는 것 (MVC와 템플릿엔진, API)

---

## #정적 컨텐츠

### i. 정적 컨텐츠란?
{: .no_toc }

> 서버에서 조작하지 않고, 파일 그대로 웹브라우저에 내려주는 것이다
>
> 이전 수업에서 html파일을 그대로 띄운 것과 같다 _(아래에 이전 수업 링크 첨부)_

[Link button](https://jgoo99.github.io/docs/backend.md/spring.md/preferences/#i-welcome-page-%EB%A7%8C%EB%93%A4%EA%B8%B0){: .btn .btn-outline }

<br/>

> 정확한 정보를 위해 _spring.io_ 에서 'static Content'를 검색해서 알아보자 _(아래에 링크 첨부)_

[Link button](https://docs.spring.io/spring-boot/docs/current/reference/html/web.html#web.servlet.spring-mvc.static-content){: .btn .btn-outline }

<br/>

_위 사이트에서 일부 스크랩_

<div class="code-example" markdown="1">
By default, Spring Boot serves static content from a directory called /static (or /public or /resources or /META-INF/resources) in the classpath or from the root of the ServletContext. 
</div>
```markdown
스프링부트가 정적 컨텐츠를 가져오는 경로에 대한 설명이다 (static이나 resources 등에서 정적 콘텐츠를 탐색함)
```

---

### ii. 웹 페이지 만들어보기
{: .no_toc }

> 위에서 설명대로 static 폴더에 html을 만들어 확인해보자

<br/>

1. html 만들기

_src/main/resources/static/hello-static.html_

```html
<!DOCTYPE HTML>
<html>
<head>
  <title>static content</title>
  <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
</head>
<body>
정적 컨텐츠 입니다.
</body>
</html>
```

<br/>

{:style="counter-reset:none"}
2. 실행 결과 확인

> intellij를 실행한 후 아래 url을 입력한다

```
localhost:8080/hello-static.html
```

![web1](https://user-images.githubusercontent.com/126454114/234172846-1efc10d8-7c86-4b80-8632-57325a57c09e.jpg)

> 출력 결과를 확인해보니 html 파일이 잘 실행되고 있다

---

### iii. 동작 방식
{: .no_toc }

![web2](https://user-images.githubusercontent.com/126454114/234173134-c6ff10b1-a0e4-4515-b257-710272e5cc96.jpg)

> 컨트롤러에서 먼저 찾아본 후 매칭이 안 되면 내부 resorces에서 매칭한다

---
---

## #MVC와 템플릿 엔진

### i. MVC와 템플릿 엔진이란?
{: .no_toc }

1. **MVC (Model View Controller)**

> 컨트롤러, 모델, 템플릿 엔진의 화면을 뜻하며, 템플릿 엔진이 동작하기 위해 필요한 것이다
>
> 각각의 역할이 무엇인지 알아보고, 명확히 분업하여 사용해야 한다 

- Model

> 컨트롤러에서 비지니스 로직이나 내부적인 것을 처리하는 것을 모델에 담아 뷰로 넘긴다

- View

> 화면을 그리는 것에 집중해야한다

- Controller

> 비지니스 로직이나 내부적인 것을 처리하는 것에 집중해야한다

{: .new-title }
> 요즘 트렌드
>
> 요즘에는 view와 controller를 쪼개는 것이 기본이다
>
> 각 파트의 코드가 굉장히 복잡하고 양이 많기 때문에 분담하여 맡는 경우가 많다

<br/>

{:style="counter-reset:none"}
2. **템플릿 엔진**

> 서버의 프로그래밍을 통해 html을 동적으로 바꾸어 전달하는 것

---

### ii. 웹 페이지 만들어보기
{: .no_toc }

> model, view, controller, 템플릿엔진을 사용하여 동적 컨텐츠를 만들어보자

<br/>

1. Controller 생성

_src/main/java/hello.hellospring/controller/HelloController.java_

```java
@Controller
public class HelloController {

  @GetMapping("hell-mvc")
  public String helloMvc(@RequestParam("name") String name, Model model) {
    //외부에서 파라미터(이름)를 받음
    model.addAttribute("name", name); //attribute name: name
    //파라미터에서 넘어온 name을 model에 담아 넘겨줌
    return "hello-template";
    //hello-template.html로 리턴
  }
}
```

<br/>

{:style="counter-reset:none"}
2. View 생성 (html)

_src/main/resources/templates/hello-template.html_

```html
<html xmlns:th="http://www.thymeleaf.org">
<body>
<p th:text="'hello ' + ${name}">hello! empty</p>
</body>
</html>
```

{: .highlight-title }
> hello! empty
>
> thymleaf의 장점 중 하나로 html의 Absolute path를 url창에 입력하면
>
> 서버 없이도 간략한 껍데기를 볼 수 있음 _아래 결과 첨부_

![web3](https://user-images.githubusercontent.com/126454114/234178639-71fe9ef7-bceb-4c02-bfa7-19717b810eab.jpg)

<br/>

{:style="counter-reset:none"}
3. 실행 결과 확인

```
localhost:8080/hello-mvc
```

![web4](https://user-images.githubusercontent.com/126454114/234181125-cb558b8a-459c-41aa-85b5-553533ce54c3.jpg)

```groovy
WARN 35856 --- [nio-8080-exec-2] .w.s.m.s.DefaultHandlerExceptionResolver : Resolved [org.springframework.web.bind.MissingServletRequestParameterException: Required request parameter 'name' for method parameter type String is not present]
```

{: .important-title }
> Warning
>
> **Required request parameter 'name' for method parameter type String is not present**
>
> name을 받지 않아서 뜨는 오류이다

<br/>

- 해결 방법

> url창에 아래와 같이 입력하여 name값을 넘길 수 있다
>
> name값을 **spring!!** 으로 넘겨보자

```
localhost:8080/hello-mvc?name=spring!!
```

![web5](https://user-images.githubusercontent.com/126454114/234183848-cb110319-ca2d-4bf3-9ec4-4818fec507d3.jpg)

```groovy
ERROR 36067 --- [nio-8080-exec-5] o.a.c.c.C.[.[.[/].[dispatcherServlet]    : Servlet.service() for servlet [dispatcherServlet] in context with path [] threw exception [Request processing failed: org.thymeleaf.exceptions.TemplateInputException: Error resolving template [hello-template], template might not exist or might not be accessible by any of the configured Template Resolvers] with root cause
```

{: .warning-title }
> Error
>
> 재실행 결과 다시 에러가 뜨는 모습을 확인할 수 있다
>
> **template might not exist or might not be accessible**
>
> 템플렛이 없거나 접근불가능하다는 내용의 에러가 떴다

<br/>

- 해결 방법

> 에러의 원인을 찾아본 결과
>
> tamplate/hello-tempat.html 파일명에 오타(e가 빠짐)가 발견되어 수정해주었다

![web6](https://user-images.githubusercontent.com/126454114/234185024-f42cd1f4-16e9-4993-8d4b-23a1319fdd4c.jpg)

> 정상적으로 화면이 출력되는 모습

---

### iii. 동작 방식
{: .no_toc }

![web7](https://user-images.githubusercontent.com/126454114/234185350-a12dfb45-23e2-4ff6-9322-95eff833c163.jpg)

- Controller

> url에 name=spring! 으로 넘겨주었기 때문에 
>
> Controller에서 name값이 **spring!으로 치환되어** model에 담긴채 view로 리턴된다

_HelloController.java_

```java
public String helloMvc(@RequestParam("name") String spring!, Model model) {
    model.addAttribute("name", spring!);
    return "hello-template";
```

<br/>

- View

> hello-template 리턴하기 때문에 뷰 리졸버가 템플릿의 같은 이름의 html파일로 넘긴다
>
> 해당 파일에서 &{name} 부분이 **spring!으로 치환되어** 랜더링한다

_hello-template.html_

```html
<p th:text="'hello ' + ${name}">hello! empty</p>
```

---
---

## #API

### i. API란?
{: .no_toc }

> json이라는 데이터 포멧으로 전달하기 위해 필요한 것이다
> 
> 1. 안드로이드/아이폰 클라이언트와 협업을 하게될 경우
>
> 2. 서버끼리 통신할 경우 (html이 필요없기 때문) _controller만 이용_

---

### ii. 웹 페이지 만들어보기
{: .no_toc }

1. 문자 반환 _(String 방식)_

- Controller 생성

```java
@GetMapping("hello-string")
@ResponseBody
public String helloString(@RequestParam("name")String name) {
  return "hello " + name; //"hello spring"
}
```

> **@ResponseBody**를 이용하여 model을 view에 전달할 필요없이
>
> 바로 http의 body에 데이터를 전달한다
>
> +) html의 body tag가 아님. 또한 http에는 헤더와 바디가 나누어짐

<br/>

- 실행 결과 확인

![web10](https://user-images.githubusercontent.com/126454114/234195094-c13f032e-121f-4d8f-bbd3-8f14103178c8.jpg)

> @ResponseBody를 통해 바로 name의 밸류를 전달하고 그대로 출력하는 모습

<br/>

{:style="counter-reset:none"}
2. 객체 반환 _(JSON 방식)_

- Controller 생성

```java
@GetMapping("hello-api")
@ResponseBody
public Hello helloApi (@RequestParam("name") String name) {
  Hello hello = new Hello();
  hello.setName(name);
  return hello;
}

static class Hello {
  private String name;

  //cmd + N : Getter and Setter 선택

  public String getName() {
    return name;
    }

  public void setName(String name) { 
  this.name = name;
  }
}
```

{: .note-title }
> Getter and Setter
>
> cmd + N 으로 사용할 수 있다
>
> 객체의 private 변수로 직접 접근이 불가능하므로 매소드를 호출하는 자바빈 방식이다

<br/>

- 실행 결과 확인

![web8](https://user-images.githubusercontent.com/126454114/234193046-2983f167-34df-4d11-af5e-df9d158233f6.jpg)

> {"key" : "value"}의 치환값이 출력되는 모습이다
>
> 요즘에 거의 jason 방식을 사용하는 추세이다

---

### iii. 동작 방식
{: .no_toc }

![web9](https://user-images.githubusercontent.com/126454114/234193676-5ab270fb-c970-4240-a58c-9ebbbb140b73.jpg)

1. 문자 반환

> @ResponsBody를 통해 바로 벨류값을 전달 받음
>
> 뷰리졸버 대신에 HttpMassageConverter가 동작함
>
> 리턴값이 문자이기 때문에 (**return "hello " + name;**) StringConverter가 동작하여 출력함

<br/>

{:style="counter-reset:none"}
2. 객체 반환

> @ResponsBody를 통해 바로 벨류값을 전달 받음
>
> 뷰리졸버 대신에 HttpMassageConverter가 동작함 _(여기까지 문자반환 방식과 동일)_
>
> 리턴값이 객체이기 때문에 (**return hello;**) JsonConverter가 동작하여 출력함

---
---

## **이번 수업 정리**
{: .no_toc }

{: .highlight }
> 기초 웹개발의 3가지 방식

<br/>

- **첫째, html만으로 정적 컨텐츠를 만들었다**

> html 파일을 만들어서 바로 웹으로 넘기면 된다
>
> _localhost:8080/static.html_

<br/>

- **둘째, MVC와 템플릿엔진을 사용하여 동적 콘텐츠를 만들었다**

> Controller에서 name키를 갖는 Model을 View에 리턴한 후 웹에서 출력한다
>
> 이때 name키의 value는 @RequestParam을 통해 url에서 받는다
>
> _localhost:8080/mvc?name=spring!!!_

<br/>

- **셋째, API 방식으로 동적 콘텐츠를 만들었다**

> 그 중 API방식은 String 반환과 객체 반환으로 나뉜다
>
> - String 반환
>
> @Responsbody를 사용하여 뷰 리졸버 대신 http메시지컨버터가 동작한다
>
> 컨버터는 문자값을 리턴받았으므로 String 방식으로 바로 출력한다
>
> - 객체 반환
> 
> @Responsbody를 사용하여 뷰 리졸버 대신 http메시지컨버터가 동작한다
>
> 컨버터는 객체를 리턴받았으므로 객체가 Json 방식으로 변환되어 웹에서 출력된다
