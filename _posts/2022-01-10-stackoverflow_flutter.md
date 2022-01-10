---
title: "스택오버플로우(Stackoverflow)의 플러터(Flutter) 질문 Best 3"
categories:
  - flutter
tags:
  - flutter
  - stackoverflow
  
toc: true
toc_sticky: true

---

> StackOverflow에 대해서 알아보고 이 곳에 게재되어 있는 질문 중 가장 높은 투표 수를 얻은 3개의 Best 질문에 대해 확인해보자.


### Stack Overflow

![img_stackOverflow](https://logovectordl.com/wp-content/uploads/2020/10/stack-overflow-logo-vector.png)

StackOverflow는 StackExchange의 대표적인 웹사이트로 개발자를 위한 개발자들에 의한 웹사이트입니다. 이 웹사이트는 컴퓨터 프로그래밍의 다양한 주제에 대한 질문과 답변의 기능을 합니다. **간단히 말해서 개발자들의 완벽한 Q&A 커뮤니티입니다**.

StackOverflow는 2008년 Jeff Atwood와 Joel Spolsky가 만들었습니다. 이 웹사이트의 이름은 2008년 4월 Atwood의 프로그래밍 블로그 'Coding Horror'의 독자 투표에 의해 선정되었다고 합니다.

이 곳에 등록된 질문과 답변에 의해 생성된 콘텐츠는 Creative Commons License에 포함됩니다. 그러므로 질문, 답변 및 모든 댓글은 자유롭게 공유 가능한 것입니다.

*전 세계 개발자들이 모여서 만든 Q&A 네트워크, 이 얼마나 멋진 일입니까?*

----------


### Best Question 3 (With Flutter Tag)

![img1]({{ site.url }}/assets/images/stackoverflow_question_1.png)

**StackOverflow에 등록된 플러터가 태그된 질문 중에서 가장 높은 득표를 받은 질문** 은 어떤 질문일지 궁금했습니다. 그래서 한번 조사해보았습니다.

> 기준일: 2022-01-11

번호 | 득표(표) | 읽은 횟수(번) | 제목
---------- | ---------- | ---------- | ----------
1 | 550 | 220,000 | How can I remove the Flutter debug banner?
2 | 453 | 368,000 | How do I use hexadecimal color strings in Flutter?
3 | 418 | 460,000 | Create a rounded button / button with border-radius in Flutter

----------

#### 1. How can I remove the Flutter debug banner?

> 플러터 디버그 배너는 어떻게 지울 수 있나요?

댓글을 통해서 2가지 방법을 알 수 있었습니다. 

첫 번째 방법인 `debugShowCheckedModeBanner` 파라미터의 `false` 설정은 평소 주로 사용하는 방법입니다.

두 번째 방법인 `Flutter Inspector` 또는 `Dart Devtools` 옵션에 `Hide Debug Mode Banner` 옵션이 있다는 건 처음 알았습니다.


- 방법 1: `MaterialApp` 파라미터 설정

```dart
MaterialApp(
  debugShowCheckedModeBanner: false,
)
```

- 방법 2: `Flutter Inspector` 또는 `Dart Devtools` 옵션 설정

![img1]({{ site.url }}/assets/images/stackoverflow_question_2.png)

----------

#### 2. How do I use hexdecimal color strings in Flutter?

> 플러터에서 16진수 색상 문자열을 어떻게 사용하나요?

간단히 아래 코드와 같이 컬러를 16진수로 지정할 수 있습니다.

```dart 
  const color = const Color(0xFFB74093);
```

추가로 VSCode나 Android Studio와 같은 IDE에서는 16진수 색상 문자열을 사용하면 `Color Picker`가 활성화되어 색상을 쉽게 확인하고 변경할 수 있습니다.

----------

#### 3. Create a rounded button / button with border-radius in Flutter

> 플러터에서 테두리가 있는 둥근 버튼 만들기

`ElevatedButton` 등 Button Widget을 사용하고 `ButtonStyle` 속성을 사용하여 Border와 Shape를 줄 수 있습니다. 예시는 다음과 같습니다.

```dart
ElevatedButton(
      style: ButtonStyle(
          shape: MaterialStateProperty.all<RoundedRectangleBorder>(
              RoundedRectangleBorder(
                  borderRadius: BorderRadius.circular(18.0),
                  side: BorderSide(
                      color: Colors.blue, 
                      width: 2.0,
                  ),
              ),
          ),
      ),
      child: Text('둥근 버튼'),
      onPressed: () {},
),
```

참고사항으로 Flutter 2.0 이후로는 `FlatButton`과 `RaisedButton`은 사용되지 않습니다.

[Flutter Gallery](https://gallery.flutter.dev/)에서 예시 이미지와 소스코드를 언제든지 열람할 수 있습니다.

----------

### 마치며

전 세계 사람들의 플러터 관련 질문 Best 3를 확인해보았습니다. 그 질문들은 어려운 질문이 아니었습니다.

세 가지 질문 외에도 득표가 높은 질문은 그렇게 어려운 질문이 아니었었습니다. 누구나 한번 쯤은 고민하고 찾아봤을 만한 질문이었습니다.

StackOverflow를 들락날락 한지는 벌써 10년 남짓이 된 듯합니다. 하지만 이렇게 StackOverflow의 특정 섹션에 대한 궁금증을 가지고 조사를 진행해본 건 처음이었습니다.

지금까지 StackOverflow를 통해서 세상의 이름 모를 개발자들에게 도움을 받았으니 저 또한 도움이 될 수 있는 엔지니어로 성장하길 바랍니다.
