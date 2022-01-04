---
title: "플러터(Flutter) 개발환경 구축하기"
categories:
  - Flutter
tags:
  - Flutter
  - development
---


> 플러터(Flutter) 개발환경을 구축해보자


### 1. 시스템 요구사항 확인
- OS : Windows 7 SP1 이상 (**Win7은 EoS로 Win10 권장**)
- Disk space : 1.64GB 이상 (IDE/Tools 제외)
- Tools
  * Windows powershell (Windows10은 기본 설치)
  * [Git for Windows](https://git-scm.com/download/win) (링크로 이동해서 설치 필수)
  * * Git 설치시 **'Use Git from the Windows Command Prompt'** 옵션 활성화
  * * 설치가 완료되면 커맨드창에서 `git` 명령어로 확인


```cmd
C:\>git
```


### 2. 플러터 다운로드 받고 설치하기
[플러터 공식 웹사이트](https://docs.flutter.dev/get-started/install/windows)에서 다운로드 및 압축 풀기


![img1]({{ site.url }}/assets/images/flutter_dev_env_1.png)


경로는 권한상승이 필요 없는 `C:\` 등의 경로로 설정해야 합니다

Git이 설치되어 있으시다면 아래 명령어로 받으셔도 됩니다


```cmd
C:\>git clone https://github.com/flutter/flutter.git -b stable
```


### 3. 환경변수 등록하기


다른 언어와 유사하게 아래 사진과 같이 **계정에 대한 환경 변수 편집**으로 들어가서 경로 추가가 필요합니다


![img2]({{ site.url }}/assets/images/flutter_dev_env_2.png)


**사용자 변수** 아래의 Path에 `flutter/bin` 경로를 추가합니다


![img3]({{ site.url }}/assets/images/flutter_dev_env_3.png)


### 4. 플러터 설치 확인하기

플러터 설치가 완료되면 새 커맨드 창을 열어서 확인할 수 있습니다


```cmd
C:\>flutter --version
```

마지막으로 `Flutter doctor` 명령어를 이용해서 플러터가 정상적으로 설치되었는지 확인할 수 있습니다.


만약에 정상적으로 설치되어 있지 않다면 어떤 설정이 추가로 필요한지 친절하게 알려줍니다.

![img4]({{ site.url }}/assets/images/flutter_dev_env_4.png)


설치가 모두 완료된 이후 Android Studio나 VSCode(VisualStudio Code)에 플러터 플러그인을 설치하면 개발환경 구축이 완료됩니다 😊


개인적으로 플러터 개발을 할 때에는 Android Studio보다는 VSCode를 주로 사용합니다. VSCode를 주로 사용하는 이유는 주로 사용하던 개발도구이기도 하고 Android Studio보다 비교적 가볍고 편하게 느껴지기 때문입니다.
{: .notice--info}


더욱 자세한 내용은 [플러터 공식 웹사이트](https://docs.flutter.dev/)에서 확인하실 수 있습니다.
