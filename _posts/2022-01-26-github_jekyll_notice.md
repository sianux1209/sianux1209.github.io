---
title: "Github blog Jekyll : Notice로 텍스트 강조하기"
categories:
- etc
tags:
  - blog
  - github
  - jekyll

toc: true
toc_sticky: true

---

> github jekyll의 Notice로 텍스트에 하이라이팅을 줄 수 있습니다. 본 포스팅은 minimal-mistakes Theme를 기준으로 작성합니다.


![img1](https://raw.githubusercontent.com/jekyll/brand/master/jekyll-logo-dark-solid.png)


----------


### Jekyll Notice Type

minimal-mistakes Theme에서는 여섯 가지 Notice Type을 제공하며 커스텀하여 Notice Type을 추가할 수 있습니다.

Notice Type | Class
---------- | ----------
Default |	.notice
Primary |	.notice--primary
Info |	.notice--info
Warning |	.notice--warning
Success |	.notice--success
Danger |	.notice--danger


----------


### Notice 예시

Type : Default
{: .notice}

Type : Primary
{: .notice--primary}

Type : Info
{: .notice--info}

Type : Warning
{: .notice--warning}

Type : Success
{: .notice--success}


----------


### Notice 사용법

```markdown
Type : Default
{: .notice}

Type : Primary
{: .notice--primary}

Type : Info
{: .notice--info}

Type : Warning
{: .notice--warning}

Type : Success
{: .notice--success}

```


