---
title: "[번역/요약] 리액트 네이티브(React Native) vs 플러터(Flutter) : 어떤 것을 사용해야 할까요?"
categories:
  - flutter
tags:
  - flutter
  - react native
  - javascript
  - dart
  
toc: true
toc_sticky: true

---

> 본 포스팅은 플러터 관련 내용을 번역/요약하여 공유하기 위한 목적으로 작성하였습니다. 

* 원문: [React Native vs Flutter: which one should you use?](https://everyday.codes/mobile/react-native-vs-flutter-which-one-should-you-use/#more-95)
* November 27, 2019 by michael krasnov
{: .align-center}, 


![img1](https://i0.wp.com/everyday.codes/wp-content/uploads/2019/11/React-Native-Vs-Flutter-Difference-1.jpg?w=1200&ssl=1)


### React Native VS Flutter

최근 몇 년 동안, 많은 기업들이 네이티브  개발에서 크로스 플랫폼으로 전환함으로써 시간과 비용을 절약할 수 있다는 것을 깨닫고 있기 때문에 크로스 플랫폼 모바일 개발 속도가 꾸준히 증가하고 있습니다. 

이를 도와주는 많은 프레임워크가 있으며 본 포스팅에서는 가장 인기있는 두 가지 프레임워크인 `리액트 네이티브(React Native)`와 `플러터(Flutter)`를 비교하겠습니다.


### 유사점

두 프레임워크는 기본적으로 `Write once, Run anywhere`라는 철학을 따릅니다.

React Native와 Flutter 앱은 Android와 IOS에서 실행됩니다. 둘 다 프레임워크로 기능이 충족되지 않을 경우 Native 코드(Kotlin/Java, Swift 등) 작성을 허용합니다.

두 프레임워크는 오픈소스입니다. 오픈소스는 누구나 소스코드를 자유롭게 접근 가능하고 코드를 작성하여 프로젝트에 직접 기여할 수 있음을 의미합니다.

React Native는 MIT 라이선스를 사용하고, Flutter은 New BSD 라이선스를 사용합니다.


### 차이점

가장 큰 차이점은 React Native와 Flutter는 서로 다른 프로그래밍 언어를 사용합니다. React Native는 JavaScript를 사용하지만 Flutter는 Dart를 사용합니다. 

Dart는 Flutter 프레임워크를 위해서 Google이 개발한 언어입니다. 일반적으로 JavaScript 관련 정보를 더 쉽게 찾을수 있으므로 React Native가 더 좋은 학습 곡선을 가질 것입니다.

또한 두 프레임워크는 앱을 패키징하는 방식에 근본적인 차이가 있습니다. React Native는 JS Runtime 및 지원 Lib가 포함된 기본 패키지와 함께 JS 코드를 제공합니다. 

그러나 Flutter를 DART 코드를 기본 기계 코드로 컴파일합니다. 즉, JS 런타임 오버헤드가 없어 성능이 향상됩니다. 성능이 문제에 결정적이라면 Flutter가 최선일 것입니다.


### 퓨시아(Fushsia) OS

Flutter에는 한 가지 트릭이 더 있습니다. Google에서 곧 출시할 OS인 Fuchsia OS는 기본적으로 Flutter를 지원합니다. Fuchsia OS가 관심을 끌 경우 Flutter 학습에 대한 투자는 더 높은 수익을 얻을 수 있을 것입니다.


### 간단히 말해서

React Native와 Flutter 중에서 선택할 때 프로젝트 요구사항과 문제를 고려해야 합니다. 이미 React를 알고 있다면 React Native를 사용하는 것이 좋습니다. 새로운 것을 배우고 싶거나 성능이 중요하다면 Flutter가 적절한 방법입니다.


### 정리

구분 | React Native | Flutter
---------- | ---------- | ----------
언어 | JavaScript | Dart
회사 | Facebook(Meta) | Google
라이선스 | MIT | New BSD

* 두 프레임워크의 지원과 성능은 유사하므로 익숙한 언어로 개발 추천
* React Native는 방대한 커뮤니티와 네트워크가 있으므로 학습 곡선에 유리
* Flutter는 2022.01 현재, 학습에 충분한 커뮤니티가 형성되어 있음
* Flutter는 Google의 차세대 OS인 퓨시아에서 지원
