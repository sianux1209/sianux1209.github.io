---
title: "Windows 환경에서 Flutter IoS App을 빌드하는 방법(With AWS EC2 mac1 Instance)"
categories:
  - Flutter
tags:
  - Flutter
  - IoS
  - AWS
  - MAC
---

# AWS(Amazone Web Service) EC2 MAC Instance 활용

![img1]({{ site.url }}/assets/images/flutter_mac_1.png)

> MAC OS가 없을 때, Windows 환경에서 AWS EC2 서비스를 이용해 Flutter로 만든 IoS App을 빌드할 수 있는 방법을 소개합니다.



Flutter에서 IoS App을 빌드하기 위해서는 기본적으로 xcode를 실행할 수 있는 MAC OS를 요구합니다.

하지만, Flutter를 시작하자마자 IoS를 만들기 위해 MAC PC를 구매하는 것은 큰 비용이 들게 됩니다.

AWS를 통해 필요한 시간만큼만 MAC을 대여해서 사용한다면 비용을 절감할 수 있고 MAC 환경을 비교적 저렴한 비용으로 경험해볼 수 있습니다.



이 방법은 Windows 환경에서 MAC을 사용하는 방법 중 **문제가 생길 경우 Apple의 지원을 받을 수 있는 방법**입니다.

해킨토시, VM(Virtual Machine) 등을 이용해 어둠의 경로로 MAC OS를 사용하는 방법도 있지만 Apple의 EULA 계약에 위배되는 내용으로 소비자 보호를 받을 수 없습니다.



## AWS EC2 MAC1 Instance
- AWS EC2(Amazon Elastic Compute Cloud)는 아마존에서 서비스하는 클라우드 컴퓨팅 서비스
- AWS EC2 서비스에서 MAC Instance를 대여하여 사용 가능
- AWS EC2 MAC Instance는 2020.11.30 시작한 서비스
- MAC Instance는 전용 호스트 서비스에서 확인 가능

![img1]({{ site.url }}/assets/images/flutter_mac_2.png)



- MAC 전용 호스트의 최소 할당 및 청구 기간 : **24시간**
- MAC Instance의 시간당 대여 비용 : **1.083 USD**

![img1]({{ site.url }}/assets/images/flutter_mac_3.png)



시간당 대여 비용이 1.083달러면 비싼 편이지만, MAC OS를 비교적 저렴한 비용을 들여 합법적으로 이용할 수 있는 방법입니다. 

다만, 최소 할당 및 청구기간이 24시간이므로 최소 소요비용은 **24 \* 1.083 = 25.992 USD, 한화로 약 31,000원** 정도 됩니다.



자세한 내용은 [AWS EC2 공식 웹사이트 링크](https://aws.amazon.com/ko/ec2/dedicated-hosts/pricing)를 참고하세요. 😊 
{: .notice--info}
