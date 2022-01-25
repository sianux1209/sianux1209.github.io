---
title: "Flutter package(pub) : 플러터 패키지 사용법"
categories:
- flutter
tags:
  - flutter
  - package
  - pub

toc: true
toc_sticky: true

---

> 플러터의 다양한 패키지를 사용하는 방법을 설명합니다


![img1](https://pub.dev/static/img/pub-dev-icon-cover-image.png?hash=vg86r2r3mbs62hiv4ldop0ife5um2g5g)

### Flutter Package?

플러터 패키지는 많은 기업과 다양한 개발자들이 Flutter와 Dart의 생태계에 공유한 패키지입니다.

이 패키지들을 활용해서 여러 가지 기능을 직접 구현하지 않고 활용할 수 있습니다.

예를 들어 Google Map, FireBase 등을 직접 구현하지 않고 구현된 라이브러리를 통해 쉽고 빠르게 적용할 수 있습니다

----------

### 플러터 패키지 사용법

#### 1. Command

```command
$ flutter pub add package_name
```

**\[TIP\]**
`flutter pub add package_name` 명령어를 실행하면 `flutter pub get` 명령어가 묵시적으로 수행됩니다.
{: .notice--info}

커맨드창에서 위 명령어를 입력하면 패키지가 다운로드 및 적용됩니다.

적용된 패키지는 `pubspec.yaml`의 `dependencies`에서 아래와 같이 확인 가능합니다.


- pubspec.yaml
  
```yaml
...

dependencies:
  flutter:
    sdk: flutter

  bloc: ^8.0.2  # flutter pub add bloc
  flutter_bloc: ^8.0.1 # flutter pub add flutter_bloc
...

```

추가로 다양한 플러터 패키지는 [pub.dev](https://pub.dev/)에서 찾아볼 수 있습니다.


#### 2. pubspec.yaml에 직접 추가

`pubspec.yaml` 파일의 `dependencies`에서 직접 패키지를 추가하고 아래 명령어를 실행해도 됩니다.

```command
$ flutter pub get
```

----------

### 플러터 패키지를 찾는 방법

[pub.dev](https://pub.dev/)에 접속해서 찾고자 하는 패키지명을 검색하면 아래 사진과 같이 관련된 여러 패키지가 나오는 것을 확인할 수 있습니다.

![img2]({{ site.url }}/assets/images/flutter_pub_1.png)

해당 패키지에 들어가면 Readme, Changelog, Installing 등 각각의 메뉴에서 패키지 설치, 사용 방법, 버전 정보 등의 확인이 가능합니다.

![img3]({{ site.url }}/assets/images/flutter_pub_2.png)

추가로 [pub.dev](https://pub.dev/)에서는 사람들에게 인기있는 패키지 또한 볼 수 있습니다.

![img4]({{ site.url }}/assets/images/flutter_pub_3.png)

어떠한 패키지가 사람들에게 인기가 있는지 확인하고 이 패키지를 통해 직접 구현해보는 방법 또한 실력 향상에 도움이 됩니다.



----------

플러터 패키지 사용 방법에 대한 자세한 내용은 [Flutter Docs](https://docs.flutter.dev/development/packages-and-plugins/using-packages) 또는 [pub.dev](https://pub.dev/)에서 확인하실 수 있습니다.
{: .notice--info}