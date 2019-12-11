---
layout: post
title: "Jekyll 운영상 문제점"
author: 박민준
date:   2019-12-04 21:32:40
tags: [solve, markdown, production]
categories: solve
---

# 버전에 따른 문제점 발생
현재 프로젝트에서 사용하는 Jekyll의 버전은 v3.8.1이다. 하지만 v3.2.0버전 이상부터는 운영 환경을 구성할 때 파일이 제대로 생성되지 않는 버그가 발생한다. 이를 해결하기 위한 방법을 찾아보았다.

## 빌드 시점에 Jekyll 환경변수 지정하기
`build` (혹은 `serve`)파라미터로, Jekyll환경 변수와 그 값을 설정 할 수 있다. 이 환경변수는 빌드 시에 사이트의 모든 조건문에서 사용된다.
예를들어 이러한 조건문이 있다고 하자.
<code>{% if( jekyll.environment == "production") %}
{% include disqus.html %}
{% endif() %} </code>
Jekyll 사이트를 빌드할 때, 다음과 같이 빌드 명령에 환경변수 `production` 을 정의하지 않으면 `if()`절 안에 들어있는 코드는 실행되지 않는다.
<code>JEKYLL_ENV=production jekyll build</code>
환경변수 값을 설정함으로써 특정 환경에서만 사용되는 컨텐츠를 만들 수 있다.

`JEKYLL_ENV`의 디폴트 값은 `development`이다. 따라서 `build`의 파라미터에 `JEKYLL_ENV`를 생략하면, `Jekyll_ENV=development`가 디폴트 값으로 사용된다. 빌드 시 `{% if( jekyll.environment == "development") %}`태그 안의 모든 컨텐츠가 출력 될 것이다.

우리가 원하는 어떤 것이든 환경변수 값으로 사용할 수 있다(반드시 `development`나 `production`일 필요는 없다.). Disqus 댓글란이나 Google Analytics 처럼 개발환경에서는 표시하고 싶지 않은 요소가 있을 수 있다. 반대로 "GitHub 에서 수정" 버튼은 개발환경에서 노출시키고 운영환경에는 포함시키지 않을 수도 있다.

빌드 명령에 옵션을 정의함으로써, 한 환경에서 다른 환경으로 환경설정 파일의 값을 수정하지 않고 이동할 수 있다.
