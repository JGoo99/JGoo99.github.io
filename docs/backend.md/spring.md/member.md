---
layout: default
title: 회원관리 예제
parent: Spring 입문
grand_parent: Back-end
nav_order: 4
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

# II. 회원관리 예제
{: .no_toc }

---

## #비지니스 요구사항 정리

### i. 데이터와 기능
{: .no_toc }

- **데이터**

> 회원 ID, 이름

- **기능**

> 회원 등록, 조회

> +)**가상의 설정**
>
> 아직 데이터 저장소 DB가 선정되지 않음
>
> RDB, NoSQL 등등 다양한 저장소를 고민중인 상황으로 가정

<br/>

### ii. 웹의 계층 구조
{: .no_toc }

![mem1](https://user-images.githubusercontent.com/126454114/234773021-936c21ff-2299-46a9-a86a-9ca9c3952946.jpg)

- **컨트롤러**

> 앞선 수업에서 다뤘던 컨트롤러와 같은 것으로, 웹 MVC에서의 역할임

- **서비스**

> 도매인 객체를 이용하여 핵심 비지니스 로직 구현
>
> 예) 중복 회원가입 막기 등

- **리포지토리**

> 데이터베이스에 접근, 도메인 객체를 DB에 저장하고 관리

- **도매인**

> 비즈니스 도메인 객체로, 주로 데이터 베이스에 저장하고 관리됨
>
> 예) 회원, 주문, 쿠폰 등

<br/>

### iii. 클래스의 의존관계
{: .no_toc }

![mem2](https://user-images.githubusercontent.com/126454114/234776031-690c7ca2-6f18-4c09-808c-eb456c6bab86.jpg)

- **MemberRepository**

> 아직 데이터 저장소 DB가 선정되지 않았기 때문에 리포지토리에 인터페이스 생성
>
> 나중에 데이터 저장소에 대한 구체적인 기술이 선정되면 메모리 리포지토리를 바꿀 예정이기 때문에 인터페이스로 정의

- **Memory MemberRepository**

> 메모리 기반의 데이터 저장소로 구현체 사용 _아직 초기 개발단계_

---

## #회원 도메인과 리포지토리 만들기

### i. 도메인 만들기
{: .no_toc }

```java
package hello.hellospring.repository;

import hello.hellospring.domain.Member;

import java.util.*;

public class MemoryMemberRipository implements MemberRepository {

  private static Map<Long, Member> store = new HashMap<>();
  private static long	sequence = 0L;

  @Override
  public Member save(Member member) {
    member.setId(++sequence);
    store.put(member.getId(), member);
    return member;
  }

  @Override
  public Optional<Member> findById(Long id) {
    return Optional.ofNullable(store.get(id));
  }

  @Override
  public Optional<Member> findByName(String name) {
	  store.values().stream()
            .filter(member -> member.getName().equals(name))
            .findAny();
  }

  @Override
  public List<Member> findAll() {
    return new ArrayList<>(store.values());
  }
}
```

---

## #회원 리포지토리 테스트 케이스 작성

---

## #회원 서비스 개발

---

## #회원 서비스 테스트

---

## **이번 수업 정리**
{: .no_toc }

{: .highlight }
> 

>