---
layout: default
title: 수열의 극한
parent: 미적분
grand_parent: Math
nav_order: 2
use_math: true
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

# I. 수열의 극한
{: .no_toc }

---

## 수열의 수렴과 발산

---

### i. 수열의 수렴과 발산
{: .no_toc }

1. **수열의 수렴**

수열 $a_n$이 일정한 극한(또는 극한값) $\alpha$에 한없이 가까워지는 것

> $\displaystyle \lim_{ n\to \infty}a_n = \alpha$


<br/>

_ex) 수열 수렴의 예시_

> $\displaystyle \lim_{n\to \infty}\frac{k}{n}=0$

<br/><br/>

{:style="counter-reset:none"}
2. **수열의 발산**

수열 $a_n$이 음이나 양의 무한대로 발산하거나 진동하는 것

> $\displaystyle \lim_{ n\to \infty}a_n = \infty$
>
> $\displaystyle \lim_{ n\to \infty}a_n = -\infty$
>
> _기타의 경우: 진동_

<br/>

_ex) 수열 발산의 예시_

> $\displaystyle \lim_{ n\to \infty}n^k=\infty$
>
> $\displaystyle \lim_{ n\to \infty}-kn=-\infty$
>
> $\displaystyle \lim_{ n\to \infty}(-1)^n$ : 진동
>
> $\displaystyle \lim_{ n]to \infty}(-k)^n$ : 진동

<br/><br/>


### ii. 수열의 극한에 관한 기본 성질
{: .no_toc }

**수렴하는 수열**의 극한에 관하여 다음 성질이 성립한다

> 수렴하는 수열 {$a_n$}, {$b_n$}에 관하여 $\displaystyle \lim_{ n\to \infty}a_n= \alpha$, $\displaystyle \lim_{ n\to \infty}b_n= \beta$이면
>
> 1. $\displaystyle \lim_{ n\to \infty}ka_n = k\alpha$
>
> 2. $\displaystyle \lim_{ n\to \infty}(a_n \pm b_n)=\alpha \pm \beta$
>
> 3. $\displaystyle \lim_{ n \to \infty}a_nb_n= \alpha\beta$
>
> 4. $\displaystyle \lim_{ n\to \infty}\frac{a_n}{b_n}=\frac{\alpha}{\beta}$ $(b_n \neq 0, \beta \neq 0)$

<br/><br/>


### iii. 수열의 극한의 대소 관계
{: .no_toc }

> 수열 {$a_n$}, {$b_n$}, {$p_n$}에 대하여
>
> 1. $a_n \leq b_n$이고, ($\displaystyle \lim_{ n\to \infty}a_n=\alpha$, $\displaystyle \lim_{ n\to \infty}b_n=\beta$)이면, $\alpha \leq \beta$
>
> 2. $a_n \leq p_n \leq b_n$이고, $\displaystyle \lim_{ n\to \infty}a_n=\lim_{n \to \infty}b_n=\alpha$이면, $\displaystyle \lim_{ n\to \infty}p_n=\alpha$

<br/>

### #연습문제

_기본문제 1)_

![image](https://github.com/JGoo99/java-project/assets/126454114/540629fd-10ab-4473-bf6a-b64850eefa9e){: width="50%""}

<br/>

_유제 1)_

![image](https://github.com/JGoo99/java-project/assets/126454114/da079a43-21fd-4087-81b1-f018ee83f207){: width="50%""}

{: .note }
> $\frac{\infty}{\infty}$ 꼴의 유리식 극한은 분모의 최고차항으로 분모, 분자를 나누어라

{: .note }
> 분모, 분자의 차수가 같을 때에는 최고차항의 계수만 생각하면 된다

<br/><br/>

_기본문제 2)_

![image](https://github.com/JGoo99/java-project/assets/126454114/b23ae088-a92f-4d3f-b601-823405bbf63f){: width="50%""}

<br/>

_유제 2)_

![image](https://github.com/JGoo99/java-project/assets/126454114/20348985-bcf8-48b3-ba1e-ae7516cb6878){: width="50%""}

![image](https://github.com/JGoo99/java-project/assets/126454114/6e9ef8e5-f61a-4da3-a675-99cc27ffe17e){: width="50%""}

{: .note }
> 수열의 합 공식을 이용하여 식을 정리한 후 극한값을 구한다

<br/><br/>

_기본문제 3)_

![image](https://github.com/JGoo99/java-project/assets/126454114/233fd094-3dfa-4a89-94a4-82fe8f7f17d0){: width="50%""}

<br/>

_유제 3)_

![image](https://github.com/JGoo99/java-project/assets/126454114/bce805e3-48fc-42d3-baf0-8871fa126971){: width="50%""}


{: .note }
> $\infty- \infty$ 꼴의 무리식의 극한은 유리화하여 구한다

<br/><br/>

_기본문제 4)_

![image](https://github.com/JGoo99/java-project/assets/126454114/f316eaa3-79a2-467f-9ff5-4824b85d0c95){: width="50%""}

<br/>

_유제 4)_

![image](https://github.com/JGoo99/java-project/assets/126454114/a2c588e5-9b5b-4b33-8cd2-86a3def8bade){: width="50%""}

{: .note }
> 부등식에서도 수열의 합과 극한값을 대입하여 비교할 수 있다

---

## 등비수열의 극한

---

### 등비수열의 수렴과 발산
{: .no_toc }



<br/>

### #연습문제

![math1](https://github.com/JGoo99/java-project/assets/126454114/ed983407-0f55-4115-bae4-6df2f5ecb5ee)

<br/>

![math2](https://github.com/JGoo99/java-project/assets/126454114/d75797ca-4865-4860-86bb-21f933e345fd)

<br/>

![math3](https://github.com/JGoo99/java-project/assets/126454114/a1275663-0ecb-405d-95e7-189b947100b8)

<br/>

![math4](https://github.com/JGoo99/java-project/assets/126454114/c467ec7f-c574-465b-8d5a-52988f5b2653)

<br/>

![math5](https://github.com/JGoo99/java-project/assets/126454114/9d0f42b7-81c0-4a7d-8721-ff8413c2b707)

<br/>

![math6](https://github.com/JGoo99/java-project/assets/126454114/311f8147-a4f1-4f8f-95ff-e81e7c5f7437)


---
