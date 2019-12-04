---
layout: post
title: "Jekyll 마크업 문제점"
author: 박민준
date:   2019-12-04 22:48:40
tags: [solve, eighth, markdown, markup]
categories: Solve
---
# 마크업 관련 문제점
Jekyll에 사용된 마크업 엔진들의 종류는 다양하고, 각 엔진에는 저마다의 특이사항이 있을 수 있다. 동일한 문제를 겪고 있는 이들에게 도움이 될 만한 정보를 여기에 모아 두었다.
## Liquid
Liquid 2.0 은 템클릿에 사용하는 {{ 가 고장난 것 같다. 이전 버전과는 다르게, 2.0 에서 {{ 를 사용하면 다음과 같은 에러가 발생한다.
```
'{{' was not properly terminated with regexp: /\}\}/  (Liquid::SyntaxError)
```
## 발췌
v1.0.0 이후부터, Jekyll에 자동으로 생성된 포스트 발췌 기능이 있었습니다. v1.1.0이후부터는, Jekyll이 이 발췌를 Liquid에 전달하게 되어 레퍼런스가 존재하지 않는다거나 태그가 올바르게 닫히지 않았다는 이상한 에러를 발생시킨다. 이런 문제가 발생하면, `_config.yml` 에 `excerpt_separator: ""` 설정을 추가하거나 이상한 문자열로 설정해 보자.
