---
layout: post
title: "Jekyll 설치 관련 문제점"
author: 박민준
date:   2019-12-04 19:30:28
tags: [solve, sixth, markdown, install]
categories: solve
---
#지킬 설치의 문제
지킬이 기반으로 하고 있는 프로그램은 Ruby Gem 이다. 이 프로그램을 리눅스 환경에서 설치 하던 중 에러가 발생하였다. 그리고 이에 대한 해결 방법을 찾아 보았다.

##설치를 위한 명령어들
우분투 또는 데비안 계열에서의 설치 명령은 다음과 같다.
<code>sudo apt-get install ruby2.3-dev</code>

레드햇이나 CentOS, 페도라에서는 다음과 같다.
<code>sudo yum install ruby-devel</code>

위 내용대로 모두 설치 했지만 확장기능이 여전히 컴파일 되지 않는다면, 아마도 ``
