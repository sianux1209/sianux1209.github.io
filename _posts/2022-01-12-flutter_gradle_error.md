---
title: "플러터(Flutter) Error - Warning: Mapping new ns to old ns ..."
categories:
  - flutter
tags:
  - flutter
  - error
  
toc: true
toc_sticky: true

---

> 플러터 개발할 때 자주 만나게 되는 `Warning: Mapping new ns to old ns ...` 에러를 해결하는 방법에 대해서 알아보자


### Error

```terminal
Warning: Mapping new ns http://schemas.android.com/repository/android/common/02 to old ns http://schemas.android.com/repository/android/common/01
Warning: Mapping new ns http://schemas.android.com/repository/android/generic/02 to old ns http://schemas.android.com/repository/android/generic/01
Warning: Mapping new ns http://schemas.android.com/sdk/android/repo/addon2/02 to old ns http://schemas.android.com/sdk/android/repo/addon2/01
Warning: Mapping new ns http://schemas.android.com/sdk/android/repo/repository2/02 to old ns http://schemas.android.com/sdk/android/repo/repository2/01
Warning: Mapping new ns http://schemas.android.com/sdk/android/repo/sys-img2/02 to old ns http://schemas.android.com/sdk/android/repo/sys-img2/01
```


### 에러가 나는 이유

이 메시지가 발생하는 이유는 Android Gradle build 과정에서 Target Android Version, Gradle Version 그리고 grade build tool Version이 맞지 않아서 발생하는 문제입니다.

Flutter는 Android와 IOS의 개발 도구에 종속적이므로 되도록이면 새로운 버전보다 안정화된 버전을 쓰는 것이 정신건강에 이롭습니다.

그럼에도 불구하고 시간이 지남에 따라 Target Android Version과 Gradle Version은 올려야 하니 이와 같은 문제가 발생하는 것입니다.


### 해결방법

1. 최신 Android sdk build-tools 설치

![img1]({{ site.url }}/assets/images/flutter_error_gradle_02.png)


2. android/build.gradle 수정 

```gradle
buildscript {
    repositories {
        google()
        mavenCentral()
    }

    dependencies {
        classpath 'com.android.tools.build:gradle:7.0.2' // Update this line
        ...
    }
}
```



### Best Question 3 (With Flutter Tag)



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