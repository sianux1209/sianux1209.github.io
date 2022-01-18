---
title: "AngularJS EOS(서비스 지원 종료)"
categories:
  - flutter
tags:
  - flutter
  - error
  
toc: true
toc_sticky: true

---

> AngularJS가 


### Error Message

![img2]({{ site.url }}/assets/images/flutter_error_gradle_01.png)

```terminal
Warning: Mapping new ns http://schemas.android.com/repository/android/common/02 to old ns http://schemas.android.com/repository/android/common/01
Warning: Mapping new ns http://schemas.android.com/repository/android/generic/02 to old ns http://schemas.android.com/repository/android/generic/01
Warning: Mapping new ns http://schemas.android.com/sdk/android/repo/addon2/02 to old ns http://schemas.android.com/sdk/android/repo/addon2/01
Warning: Mapping new ns http://schemas.android.com/sdk/android/repo/repository2/02 to old ns http://schemas.android.com/sdk/android/repo/repository2/01
Warning: Mapping new ns http://schemas.android.com/sdk/android/repo/sys-img2/02 to old ns http://schemas.android.com/sdk/android/repo/sys-img2/01
```

----------


### 에러가 나는 이유

Project의 Android SDK Version이 30 이상이면 이 에러를 만날 수 있습니다.

이 에러가 발생하는 이유는 Android Gradle build 과정에서 Target Android Version, Gradle Version 그리고 Grade build tool Version이 맞지 않아서 발생하는 문제입니다.

Flutter는 Android와 IOS의 라이브러리에 종속적이기 때문에 되도록이면 **새로운 버전보다 안정화된 버전을 쓰는 것이 정신건강에 이롭습니다.**

그럼에도 불구하고 시간이 지남에 따라 Target Android Version과 Gradle Version은 올려야 하니 이와 같은 문제가 발생하는 것입니다.

그래서 이 문제를 해결하기 위해서는 Gradle과 Gradle build tool의 Version을 맞춰주면 해결됩니다. 해결 방법은 아래서 설명합니다.


----------

### 해결 방법

> 간단한 해결 방법은 Android SDK Version을 29로 낮추면 해결됩니다.

> Android SDK Version을 30 이상으로 유지하면서 Error를 슈팅하고 싶다면 아래와 같이 진행하시면 됩니다.


#### 1.`android/build.gradle` 수정 

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

2022.01.12 기준, Google Maven Repository에 Gradle build tool의 안정된 릴리즈 버전은 7.0.4이지만 Flutter Porject 특성상 조금이라도 높은 버전은 에러가 날 가능성이 있으므로 Stackoverflow에서 개발자들이 사용한 버전인 7.0.2 사용
{: .notice--info}

----------


#### 2.`android/gradle/wrapper/gradle-wrapper.properties` 수정

```properties
...
distributionUrl=https\://services.gradle.org/distributions/gradle-7.2-all.zip # Update this line

```

Gradle 또한 Build tool과 동일한 사유로 현재 Stable release 버전을 사용합니다. 7.2 버전은 제가 에러 없이 테스트 빌드에 성공한 Version
{: .notice--info}


----------

#### 3.최신 Android SDK build-tools 설치

> 2번까지 진행하면 에러는 잡힐 가능성이 높습니다. 하지만 SDK Build tool을 업데이트 하고 에러를 해결했다는 사람도 있고, Android 개발을 계속 할 것이니 업데이트 해줍니다.

![img2]({{ site.url }}/assets/images/flutter_error_gradle_02.png)


----------

### 마치며

플러터는 Cross-Platform Framework이기 때문에 Android와 IOS 등 OS의 라이브러리와 플러그인에 종속적인 특성이 있습니다. 그렇기 때문에 이와 같은 에러를 시도때도 없이 만나게 됩니다.

다른 개발 프로젝트보다 트러블슈팅에 대한 글이 적은 것도 사실입니다.  하지만 이런 문제를 직접 해결해가는 것도 실력 향상에 도움이 될 것이라고 생각합니다. 실제로도 에러 메시지를 유심히 보게 되는 것 같기도 합니다.

앞으로 개발하면서 자주 만나는 에러에 대한 해결 방법은 정리해서 포스팅할 계획입니다.
