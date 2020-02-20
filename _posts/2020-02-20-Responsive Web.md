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

Media Query 는 CSS3 에 포함되어 있으며, 자바스크립트 등을 사용하지 않고도 특정 요소에 <span class="orange">해상도별로 대응하는 스타일을 각각 적용시킬 수 있도록 해준다.</span> 정확히는 Media Type 를 이용한 표현식을 통해 <span class="orange">스타일의 적용 범위를 한정할 수 있다.</span> Media Query 는 Media Type 과 하나 이상의 Width, Height 와 같은 Media Feature로 이루어진 조건식으로 구성된다. 이때 Media Type 은 CSS가 해석되는 디바이스의 종류에 따라 각기 다른 스타일을 적용할 수 있도록 해주며, Only 혹은 Not 키워드로 명시하지 않는한 Media Type은 선택적이며 all 타입으로 간주 된다. Media Type은 모든 디바이스에 대응되는 all, 컴퓨터 화면과 스마트폰 화면에 대응되는 screen, 프린트 용도에 대응되는 print 를 포함한 많은 타입을 가지고 있다.

## 기본설정

반응형웹을 적용하기 위해서는 먼저 <span class="gray">meta viewport</span>를 설정해 줘야 합니다.  
meta viewport의 width를 device-width로 지정하고 initial-scale을 1로 설정을 해 줘야 합니다.  
<span class="orange">width=device-width</span> : 화면의 넓이를 디바이스(단말기)의 넓이로 지정  
<span class="orange">initial-scale=1</span> : 기본 사이즈를 1로 지정하겠다고 선언

<div class="code">
<iframe width="100%" height="100" src="//jsfiddle.net/lsh58/7mnfa5qL/5/embedded/css/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

이렇게 설정하면 다양한 크기의 화면에서도 보기에 편한 텍스트 크기와 레이아웃을 유지해 줍니다.

## 기본 형태

미디어 쿼리의 기본적인 형태는 다음과 같다.

<div class="code">
<iframe width="100%" height="150" src="//jsfiddle.net/lsh58/7mnfa5qL/1/embedded/css/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>
  
Only 혹은 Not 키워드를 사용하여 Media Type 을 정해주고, and 연산자를 사용하여 조건식을 묶어준다. 조건식은 Feature: Value 형식으로 작성한다. 실행문에는 일반적인 CSS 코드를 넣는다. 실행문에 넣어준 CSS 코드는 조건이 만족할때만 적용되며 그 이외에 상황에서는 적용되지 않는다.

## 조건식을 이루는 대표적인 Media Feature

<span class="orange">width (max-width, min-width) / height (max-height, min-height)</span>  
뷰포트의 너비와 높이를 나타낸다. 뷰포트의 크기는 HTML 컨텐츠의 내용을 표시하는 전체적인 크기를 말하며, 화면의 크기와는 거리가 있는 개념이다.  
<span class="orange">device-width / device-height</span>  
디바이스가 출력할 수 있는 영역의 크기, 즉 스크린의 해상도를 의미한다.  
<span class="orange">orientation</span>  
화면이 세로모드인지 가로모드인지 판단할 수 있다. 이를 판단하는 기준은 뷰포트의 너비와 높이의 비율이다.  
<span class="orange">aspect-ratio (max-aspect-ratio, min-aspect-ratio)</span>  
스크린의 너비와 높이의 비율. Value 는 너비/높이 형태로 작성한다. 너비와 높이의 비율을 4:5로 하고싶다면 4/5로 작성하면 된다.  

## 미디어쿼리 지정

기본설정을 했으면 이번에 다양한 크기(해상도)의 디바이스에 따라 CSS가 다르게 적용될 수 있게 미디어쿼리(Media Query)를 지정해야 합니다.
Breakpoints는 부트스트랩(Bootstrap)을 참조하였으며 그에 해당하는 미디어쿼리는 아래와 같이 가로 해상도에 따라 5가지로 구분할 수 있습니다.

반응형 웹개발에 있어서 고려해야 할 점이 있는데 모바일 퍼스트 로 개발을 할 것이냐 하는 것입니다.
모바일 퍼스트 개발은 화면 구현 시 먼저 모바일 화면을 기준으로 디자인(CSS)을 하고 차츰 태블릿 화면, 데스트탑 화면으로 디자인을 구현하는 것을 말합니다.
반응형 웹개발 시 근래의 추세는 모바일 퍼스트로 개발하는 추세이긴 합니다만 상황에 따라서 데스크탑 퍼스트(사실 데스크탑 퍼스트라는 말을 잘 쓰지는 않습니다.)로 개발하는 경우도 빈번합니다.

### 모바일 퍼스트 개발

반응형 웹개발에 있어서 모바일 퍼스트 개발은 근래에 선호되는 방법입니다.  
모바일 퍼스트로 개발할 경우는 미디어쿼리도 max-width가 아니라 min-width방식으로 지정하여 사용하고
CSS의 Override 특성을 활용하여 미디어쿼리를 작성하면 됩니다.

가장 작은 디바이스 : 가로 해상도가 576px 보다 작은 모든 디바이스를 기본으로 CSS를 작성합니다.  
모바일 디바이스 : 가로 해상도가 576px 보다 큰 경우의 모바일 디바이스에 대한 CSS를 작성합니다.  
태블릿 디바이스 : 가로 해상도가 768px 보다 큰 경우의 테블릿 디바이스에 대한 CSS를 작성합니다.  
데스크탑 : 가로 해상도가 992px 보다 큰 경우의 데스크탑에 대한 CSS를 작성합니다.  
큰화면의 데스크탑 : 가로 해상도가 1200px 보다 큰 경우의 데스크탑에 대한 CSS를 작성 합니다.  

<div class="code">
<iframe width="100%" height="350" src="//jsfiddle.net/lsh58/7mnfa5qL/6/embedded/css/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

만약@media (min-width: 768px) { ... }까지만 작성하고
@media (min-width: 992px) { ... }와 @media (min-width: 1200px) { ... }에 대한 미디어쿼리를 작성하지 않았다면
@media (min-width: 768px) { ... }에 정의된 CSS가 테스크탑과 큰화면의 데스크탑의 크기에도 동일하게 적용이 됩니다.

### 데스크탑 퍼스트 개발

모바일퍼스트에 반대되는 개발 방법으로 예전에 많이 사용되었던 방식입니다.  
데스크탑 화면이 중요하거나 또는 기존에 개발되어 있던 데스크탑 화면의 CSS에 모바일 화면에 대한 추가 개발을 해야 할 경우에 많이 사용합니다.
이럴경우 모바일 퍼스트로 개발하는 것과 반대로 미디어쿼리도 min-width가 아니라 max-width방식으로 지정하여 사용 합니다.

가장 작은 디바이스 : 가로 해상도가 576px 보다 작은 모든 디바이스를 기본으로 CSS를 작성합니다.  
모바일 디바이스 : 가로 해상도가 576px 보다 큰 경우의 모바일 디바이스에 대한 CSS를 작성합니다.  
태블릿 디바이스 : 가로 해상도가 768px 보다 큰 경우의 테블릿 디바이스에 대한 CSS를 작성합니다.  
데스크탑 : 가로 해상도가 992px 보다 큰 경우의 데스크탑에 대한 CSS를 작성합니다.  
큰화면의 데스크탑 : 가로 해상도가 1200px 보다 큰 경우의 데스크탑에 대한 CSS를 작성 합니다.  

<div class="code">
<iframe width="100%" height="300" src="//jsfiddle.net/lsh58/7mnfa5qL/8/embedded/css/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

만약 @media (max-width: 767px) { ... }까지만 작성하고
@media (max-width: 575px) { ... }에 대한 미디어쿼리를 작성하지 않았다면..
@media (max-width: 767px) { ... }에 정의된 CSS가 세로모드 모바일 디바이스와 가로모드 모바일 디바이스의 크기에도 동일하게 적용이 됩니다.

### 해상도 범위 지정 CSS 개발

나머지는 CSS의 Override기능을 사용하지 않고 지정된 해상도를 설정하여 사용하는 방법입니다.  
미디어쿼리를 가장 작은 해상도와 가장 큰 해상도의 범위를 명확히 지정하여 사용 합니다.  
이럴경우 미디어쿼리는 min-width와 max-width를 동시에 지정하여 사용 합니다.  

가장 작은 디바이스 : 가로 해상도가 576px 보다 작은 모든 디바이스를 기본으로 CSS를 작성합니다.  
모바일 디바이스 : 가로 해상도가 576px 보다 크고 767px보다 작은 모바일 디바이스에 대한 CSS를 작성합니다.  
태블릿 디바이스 : 가로 해상도가 768px 보다 크고 991px보다 작은 테블릿 디바이스에 대한 CSS를 작성합니다.  
데스크탑 : 가로 해상도가 992px 보다 큰고 1199px보다 작은 데스크탑에 대한 CSS를 작성합니다.  
큰화면의 데스크탑 : 가로 해상도가 1200px 보다 큰 경우의 데스크탑에 대한 CSS를 작성 합니다.  

<div class="code">
<iframe width="100%" height="330" src="//jsfiddle.net/lsh58/7mnfa5qL/10/embedded/css/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

<br>

출처 : <https://hudi.kr/css3-media-query-%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-%EB%B0%98%EC%9D%91%ED%98%95-%EC%9B%B9-%EB%A7%8C%EB%93%A4%EA%B8%B0/>
<https://blog.stories.pe.kr/199>
