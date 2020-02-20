---
layout: post
title: "Responsive Web"
description:
headline:
modified: 2020-02-20
category: webdevelopment
tags: [CSS]
imagefeature:
mathjax:
chart:
share: true
comments: true
featured: true
---

# Media Query

Media Query 는 CSS3 에 포함되어 있으며, 자바스크립트 등을 사용하지 않고도 특정 요소에 해상도별로 대응하는 스타일을 각각 적용시킬 수 있도록 해준다. 정확히는 Media Type 를 이용한 표현식을 통해 스타일의 적용 범위를 한정할 수 있다. Media Query 는 Media Type 과 하나 이상의 Width, Height 와 같은 Media Feature로 이루어진 조건식으로 구성된다. 이때 Media Type 은 CSS가 해석되는 디바이스의 종류에 따라 각기 다른 스타일을 적용할 수 있도록 해주며, Only 혹은 Not 키워드로 명시하지 않는한 Media Type은 선택적이며 all 타입으로 간주 된다. Media Type은 모든 디바이스에 대응되는 all, 컴퓨터 화면과 스마트폰 화면에 대응되는 screen, 프린트 용도에 대응되는 print 를 포함한 많은 타입을 가지고 있다.

## 기본 형태

미디어 쿼리의 기본적인 형태는 다음과 같다.

<div class="code">
<iframe width="100%" height="300" src="//jsfiddle.net/lsh58/7mnfa5qL/1/embedded/css/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>
  
Only 혹은 Not 키워드를 사용하여 Media Type 을 정해주고, and 연산자를 사용하여 조건식을 묶어준다. 조건식은 Feature: Value 형식으로 작성한다. 실행문에는 일반적인 CSS 코드를 넣는다. 실행문에 넣어준 CSS 코드는 조건이 만족할때만 적용되며 그 이외에 상황에서는 적용되지 않는다.

## 조건식을 이루는 대표적인 Media Feature

width (max-width, min-width) / height (max-height, min-height)
뷰포트의 너비와 높이를 나타낸다. 뷰포트의 크기는 HTML 컨텐츠의 내용을 표시하는 전체적인 크기를 말하며, 화면의 크기와는 거리가 있는 개념이다.

device-width / device-height
디바이스가 출력할 수 있는 영역의 크기, 즉 스크린의 해상도를 의미한다.

orientation
화면이 세로모드인지 가로모드인지 판단할 수 있다. 이를 판단하는 기준은 뷰포트의 너비와 높이의 비율이다.

aspect-ratio (max-aspect-ratio, min-aspect-ratio)
스크린의 너비와 높이의 비율. Value 는 너비/높이 형태로 작성한다. 너비와 높이의 비율을 4:5로 하고싶다면 4/5로 작성하면 된다.

반응형웹을 만들기 위해 자주 사용되는 대표적인 세가지 max-width값은 다음과 같다.

<div class="code">
<iframe width="100%" height="300" src="//jsfiddle.net/lsh58/7mnfa5qL/2/embedded/css/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

출처 : <https://hudi.kr/css3-media-query-%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-%EB%B0%98%EC%9D%91%ED%98%95-%EC%9B%B9-%EB%A7%8C%EB%93%A4%EA%B8%B0/>
<https://blog.stories.pe.kr/199>
