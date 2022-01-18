---
title: "앵귤러JS(AngularJS) EOL(서비스 지원 종료)"
categories:
- security
tags:
  - angularjs
  - eol
  - eos
  - security

toc: true
toc_sticky: true

---

> AngularJS의 지원 기간이 21.12.31일자로 만료되어 EOL(End of Life:서비스 지원 종료) 일정에 들어갔다. 

> 혹시나 아직 AngularJS를 쓰는 곳이라면 보안위협에 노출될 가능성이 있기 때문에, 프레임워크를 업그레이드하거나 다른 프레임워크로 신속히 전환하기를 바란다.


### AngularJS

![img1](https://logowik.com/content/uploads/images/angularjs-by-google1122.jpg)

AngluarJS는 Angluar의 1.X 버전을 말하며, 이후 2.X 이후 버전을 Angluar라고 칭합니다.
{: .notice--info}

AngularJS는 Javascript 기반 오픈소스 프론트엔드 웹 어플리케이션 프레임워크의 하나입니다. SPA(Single Page Application) 등의 여러 문제들을 해결하기 위해 탄생하였습니다.

2009년 Google 직원인 Misko hevery와 Adam sbrons에 의해 최초 개발되었으며 2010.10.20 발표되었습니다. 

주로 구글과 개별 커뮤니티에 의해 유지보수되고 있으며 MVC 모델과 MVVC 구조를 위한 프레임워크를 제공함으로써 웹 어플리케이션의 개발 및 테스트를 지원합니다. 

간단히 말해서 많은 개인과 기업들은 AngularJS를 사용함으로 인해서 개발 생산성이 향상되는 효과를 얻었습니다.

**2021.12.31 EOL된 프레임워크입니다.**

----------


### [AngularJS의 EOL(서비스 지원 종료)](https://docs.angularjs.org/misc/version-support-status)

![img2]({{ site.url }}/assets/images/angularjs_eos_1.png)

AngularJS는 2018.07.01 LTS 지원에 들어갔습니다. 그리고 2021.06.30 EOL 예정이었으나 **COVID-19의 영향으로 LTS 지원을 2021.12.31일까지 6개월 연장하였습니다.**

**AngularJS EOL 일정 : 2021.12.31**
{: .notice--danger}

EOL로 인해서 여러 가지 지원이 종료되지만 가장 중요한 것은 **보안 업데이트가 더이상 지원되지 않는다는 사실입니다.**

혹시나 아직도 AngularJS를 사용하는 개인 또는 기업이 있다면 [Angular](https://angular.io/)로의 업데이트를 수행하거나 [AngularJS XLTS 파트너](https://xlts.dev/angularjs)에게 지원을 요청하시기 바랍니다. 또는 다른 프레임워크로 전환하는 방법도 있습니다.

 Angular은 AngularJS의 후속버전이고, AngularJS XLTS 파트너는 EOL된 프레임워크를 지원하기 위한 커뮤니티 그룹입니다.


----------


### EOL(서비스 지원 종료)로 인한 영향

AngularJS 프레임워크가 EOL 됨으로 인해서 여러 가지 문제 또는 사고가 발생할 수 있습니다. 예를 들어 발생 가능한 문제는 **ⓐ보안취약점, ⓑ버그, ⓒ시스템 호환성** 등의 문제 등입니다.

**이 중에서 발생 가능한 가능 큰 문제는 취약점으로 인한 보안사고 입니다. 더이상 서비스를 지원하지 않는 서비스에서는 취약점 패치가 어렵습니다.**

더욱이 실제 서비스에서 보안사고가 발생한다면 그 결과는 기업의 큰 손실로 나타날 가능성이 있습니다. 그렇기 때문에 **EOL 예정인 서비스는 신속한 프레임워크의 전환이 필요합니다.**


----------

### 마치며

AngularJS를 아직도 사용하는 기업이 있겠나 싶어 조사를 해보았습니다. 놀라운 사실은 2022.01 현재 EOL 되었음에도 불구하고 비즈니스에 AngularJS를 사용하고 있는 서비스가 존재했으며 채용을 진행하는 기업도 있었습니다.

발생해서는 안되는 일이지만, 머지않아 EOL된 AngularJS를 사용하는 서비스에 해킹사고가 발생했다는 뉴스를 볼 것만 같습니다. 보안사고가 발생하지 않기를 기도합니다🙄


AngularJS의 EOL에 대한 공식적인 내용은 [AngularJS 공식홈페이지](https://angularjs.org)에서 확인하실 수 있습니다.
{: .notice--info}