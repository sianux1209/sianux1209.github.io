---
title: "마크다운 문법 정리 (Markdown Cheatsheet)"
categories:
  - etc
tags:
  - markdown
  - cheatsheet
toc: true
toc_sticky: true

---

> 마크다운(Markdown) 문법을 간단하게 Cheatsheet 형식으로 요약

### Basic Rule

규칙명 | 사용법
---------- | ----------
Heading1 | `# comment`
Heading2 | `## comment`
Heading3 | `### comment`
Heading4 | `#### comment`
Heading5 | `##### comment`
Heading6 | `###### comment`
italic | `*comment*`
bold | `**comment**`
strikethrough | `~~comment~~`
code | \`comment\`
horizontal rule | `----------`
image | `![이미지명](/images/markdown.jpg)`
link | `[링크명\](https://naver.com)`

----------


### Fenced codeblock


\`\`\`python

print\("example"\)

\`\`\`

----------


### Ordered list

```md
1. first
2. second
```

----------


### Unordered list 

```md
- first
- second
```


----------


### Quote

```md
> first
> second
```

----------

### Emphasis

```md
* first
* second
```

----------

### Indent

```md
1. first
    - secnond
        > third
            * fourth
```
