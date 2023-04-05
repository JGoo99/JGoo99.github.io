---
layout: default
title: Memo
nav_order: 99
---

### 버튼만들기

#### 다크모드 버튼

<button class="btn js-toggle-dark-mode">Preview dark color scheme</button>

<script>
const toggleDarkMode = document.querySelector('.js-toggle-dark-mode');

jtd.addEvent(toggleDarkMode, 'click', function(){
  if (jtd.getTheme() === 'dark') {
    jtd.setTheme('light');
    toggleDarkMode.textContent = 'Preview dark color scheme';
  } else {
    jtd.setTheme('dark');
    toggleDarkMode.textContent = 'Return to the light side';
  }
});
</script>

#### 기본 버튼

<div class="code-example" markdown="1">
[Link button](http://example.com/){: .btn }

[Link button](http://example.com/){: .btn .btn-purple }
[Link button](http://example.com/){: .btn .btn-blue }
[Link button](http://example.com/){: .btn .btn-green }

[Link button](http://example.com/){: .btn .btn-outline }
</div>

#### Button element

GitHub Flavored Markdown does not support the `button` element, so you'll have to use inline HTML for this:

<div class="code-example">
<button type="button" name="button" class="btn">Button element</button>
</div>
```html
<button type="button" name="button" class="btn">Button element</button>
```

#### 버튼 크기


<div class="code-example" markdown="1">
<span class="fs-6">
[Big ass button](http://example.com/){: .btn }
</span>

<span class="fs-3">
[Tiny ass button](http://example.com/){: .btn }
</span>
</div>

#### 버튼 사이 공간 만들기

<div class="code-example" markdown="1">
[Button with space](http://example.com/){: .btn .btn-purple .mr-2 }
[Button](http://example.com/){: .btn .btn-blue }

[Button with more space](http://example.com/){: .btn .btn-green .mr-4 }
[Button](http://example.com/){: .btn .btn-blue }
</div>

---

### 굵은 글씨, 기울임, 글씨 가운데 줄긋기

Text can be **bold**, _italic_, or ~~strikethrough~~.

### 박스 만들기

ABCDEFGHIJKLMNOPQRSTUVWXYZ
abcdefghijklmnopqrstuvwxyz
{: .fs-5 .ls-10 .text-mono .code-example }

### 긴 글 넣고 싶을 때

<div class="code-example" markdown="1">
Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
</div>
```markdown
박스 붙여서 짧은 글을 쓸 수 있음
```

### 글씨 크기

<div class="code-example" markdown="1">
Font size 1
{: .fs-1 }
Font size 2
{: .fs-2 }
Font size 3
{: .fs-3 }
Font size 4
{: .fs-4 }
Font size 5
{: .fs-5 }
Font size 6
{: .fs-6 }
Font size 7
{: .fs-7 }
Font size 8
{: .fs-8 }
Font size 9
{: .fs-9 }
Font size 10
{: .fs-10 }
</div>

### 글씨 굵기
<div class="code-example" markdown="1">
Font weight 300
{: .fw-300 }
Font weight 400
{: .fw-400 }
Font weight 500
{: .fw-500 }
Font weight 700
{: .fw-700 }
</div>

---

### 링크걸기

[Link to another page](another-page).

[This is a very long link which wraps and therefore doesn't overflow
even when it comes at the beginning](.) of the line.

- [This is a very long link which wraps and therefore doesn't overflow the line
  when used first in an item ](.) in a list.

---

### 단락 제목

# [](#header-1)Header 1

## [](#header-2)Header 2

### [](#header-3)Header 3

#### [](#header-4)Header 4 `with code not transformed`

##### [](#header-5)Header 5

###### [](#header-6)Header 6

---

### 들여쓰기

> This is a blockquote following a header.
> 안녕하세요.

---

### 코드 작성

```java
package dynamic_beat_1;

import javax.swing.JFrame;

public class DynamicBeat  extends JFrame {

	public DynamicBeat() {
		setTitle("Dynamic Beat");
```

---

### 줄 나누기

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

### 하위목록 만들기

- level 1 item
  1. level 2 item
  2. level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  1. level 2 item
  2. level 2 item
  3. level 2 item
    - level 3 item

### 번호 나누기

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

_번호 안 끊기게 할 수 있음_

{:style="counter-reset:none"}
4.  Item three
5.  Item four 

_원하는 숫자부터 시작할 수 있음_

{:style="counter-reset:step-counter 41"}
1.  Item 42
1.  Item 43
1.  Item 44

---

### 표 만들기

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

---

### 체크리스트 만들기

- level 1 item (task)
   - [ ] level 2 item (task)
   - [x] level 2 item (task)
- level 1 item (task)
- [x] level 1 item (task)

---

### 이미지 삽입

작은 이미지

![](../../assets/images/small-image.jpg)

큰 이미지

![](../../assets/images/large-image.jpg)

"[Wroclaw University Library digitizing rare archival texts](https://www.flickr.com/photos/97810305@N08/9401451269)" by [j_cadmus](https://www.flickr.com/photos/97810305@N08) is marked with [CC BY 2.0](https://creativecommons.org/licenses/by/2.0/?ref=openverse).

---

### 라벨 넣기

blue
{: .label .label-blue }
green
{: .label .label-green }
purple
{: .label .label-purple }
yellow
{: .label .label-yellow }
red
{: .label .label-red }

---



### 다이어그램 넣기

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

