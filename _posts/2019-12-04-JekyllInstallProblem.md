---
layout: post
title: "Jekyll 설치 관련 문제점"
author: 박민준
date:   2019-12-04 22:02:28
tags: [solve, sixth, markdown, install]
categories: Solve
---
# 지킬 설치의 문제
지킬이 기반으로 하고 있는 프로그램은 Ruby Gem 이다. 이 프로그램을 리눅스 환경에서 설치 하던 중 에러가 발생하였다. 그리고 이에 대한 해결 방법을 찾아 보았다.

## 설치를 위한 명령어들
우분투 또는 데비안 계열에서의 설치 명령은 다음과 같다.
<code>sudo apt-get install ruby2.3-dev</code>

레드햇이나 CentOS, 페도라에서는 다음과 같다.
<code>sudo yum install ruby-devel</code>

위 내용대로 모두 설치 했지만 확장기능이 여전히 컴파일 되지 않는다면, 아마도 `redhat-rpm-config`패키지가 포함되지 않은 페도라 이미지를 사용하고 있는 것일 수 있다. 이를 해결하려면, 아래와 같이 실행해야 한다.
<code>sudo dnf install redhat-rpm-config</code>

아치 리눅스에서는 이렇게 실행해야 한다.
<code>sudo pacman **-S** ruby-ffi</code>

우분투에서 `bundle exec jekyll serve`를 실행한 후 `Could not locate Gemfile or .bundle/ directory`라는 에러 메세지가 나온다면, 모든 필요조건이 만족되지 ㅇ낳았을 가능성이 높다. 최근의 우분투 배포판들은 `ruby`와 `ruby-all-dev` 패키지를 모두 필요로 한다.
<code>sudo apt-get install ruby ruby-all-dev</code>

**NearlyFreeSpe** 에서는 Jekyll을 설치하기 전에 다음 명령어를 실행해야 한다.
<code>export GEM_HOME=/home/private/gems
export GEM_PATH=/home/private/gems:/usr/local/lib/ruby/gems/1.8/
export PATH=$PATH:/home/private/gems/bin
export RB_USER_INSTALL='true'</code>

전투에 RubyGems 를 설치하려면 다음 명령을 실행합니다.
<code>sudo emerge **-av** dev-ruby/rubygems</code>

윈도우즈 에서는, **RubyInstaller DevKit** 를 설치해야 할 수 도 있다.

안드로이드에서는 다음 명령으로 필요한 모든 것을 설치 할 수 있다.
<code>apt update && apt install libffi-dev clang ruby-dev make</code>

맥OS 에서는, RubyGems를 업데이트해야 할 수도 있습니다(반드시 필요한 경우에만 `sudo`와 함께 실행함).
<code>gem update **--system**</code>

여전히 문제가 해결되지 않는다면, 새 명령행 도구를 설치하기 위해 다음 명령을 실행한다.
<code>xcode-select **--install**</code>

그 다음, 이 명령으로 Native루비 젬을 설치할 수 있게 됩니다.
<code>gem install jekyll</code>

맥OS를 업그레이드 한다고 해서 Xcode까지 자동으로 업그레이드 되지는 않는다는 것과 최신 버전이 아닌 Xcode.app은 앞서 설명한 명령행 도구와 충돌을 일으킬 수 있다는 점에 주의해야 한다. 이런 문제가 발생한다면, Xcode를 업그레이드 하고 최신 명령행 도구를 설치해야 한다.
