---
layout: post
title: "Jekyll 환경설정 문제점"
author: ss_choi
date:   2019-12-03 22:32:30
tags: [solve, markdown, setting]
categories: solve
---
# 환경설정 관련 문제점
**환경설정** 이 충돌하는 경우의 우선순위는 다음과 같다.
* 1. 명령형 플래그
  2. 환경설정 파일
  3. 디폴트 값

한 마디로 정리하면 이런 뜻이다.
환경설정 파일 `_config.yml` 에 설정된 옵션이 디폴트값 대신 사용되고, 명령행에 사용된 플래그들은 다른 모든 설정들 보다 우선순위가 높다.

#### 메모 : 버전 v3.3.0 부터는, `node_modules` 와 `vendor` 안의 몇몇 하위 디렉토리들은 처리하지 않는 것이 Jekyll의 기본 동작 방식이다. 하지만 환경설정 파일에 `exclude:` 배열을 명시적으로 설정하여 이 기본 동작방식을 조정할 수 있는데, 이로 인해 몇몇 사용자들에게는 사이트 생성 시 다음과 같은 내용의 에러가 발생할 수도 있다.
```
ERROR: YOUR SITE COULD NOT BE BUILT:
    ------------------------------------
    Invalid date '<%= Time.now.strftime('%Y-%m-%d %H:%M:%S %z') %>':
    Document 'vendor/bundle/gems/jekyll-3.4.3/lib/site_template/_posts/0000-00-00-welcome-to-jekyll.markdown.erb'
    does not have a valid date in the YAML front matter.
```  
단순히 `vendor/bundle` 을 `exclude:` 목록에 추가하는 것 만으로 이 문제를 해결할 수 있지만, `/vendor/` 의 하위 디렉토리들(존재하는 경우 `/node_modules/` 포함)이 최종 결과물 경로인 `_site` 안에도 생성된다.

자신의 설정에 기본 exclude: 설정을 포함시키는 쪽이 완전히 덮어쓰는 방법보다 더 수월하다.

버전 v3.4.3 까지, exclude: 설정은 다음과 같다.
```
exclude:
  - Gemfile
  - Gemfile.lock
  - node_modules
  - vendor/bundle/
  - vendor/cache/
  - vendor/gems/
  - vendor/ruby/
  - any_additional_item # any user-specific listing goes at the end
```
버전 `v3.5` 부터, 기본 설정으로 `Gemfile` 과 `Gemfile.lock` 도 제외된다. 따라서, 특별한 경우가 아닌 이상 환경설정 파일에 추가로 `exclude:` 배열을 정의할 필요가 없다. 또한 기본 설정에 이미 정의된 내용도 위와 같이 수정하거나, 아니면 완전히 제거하거나, 나중을 위해 단순히 주석 처리할 수 있다.
