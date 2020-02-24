---
layout: post
title: "Inline, Block, Inlineblock"
description:
headline:
modified: 2020-02-17
category: webdevelopment
tags: [CSS]
imagefeature:
mathjax:
chart:
share: true
comments: true
featured: true
---

# Display속성 : Inline

display 속성이 inline으로 지정된 엘리먼트는 전후 줄바꿈 없이 한 줄에 다른 엘리먼트들과 나란히 배치됩니다.  
text 크기만큼만 공간을 점유하고 줄바꿈을 하지 않습니다.  
대표적인 inline 엘리먼트로 <span class="orange">< span ></span>이나 <span class="orange">< a ></span>, <span class="orange">< em ></span> 태그 등을 들 수 있습니다.

<span class="blackbox">width/height 적용불가</span>

<span class="blackbox">margin/padding-top/bottom 적용불가 (left/right는 적용가능)</span>

<span class="blackbox">line-height를 원하는대로 사용할 수 없다.</span>

# Display속성 : Block

display 속성이 block으로 지정된 엘리먼트는 전후 줄바꿈이 들어가 다른 엘리먼트들을 다른 줄로 밀어내고 혼자 한 줄을 차지합니다.  
대표적인 block 엘리먼트로 <span class="orange">< div ></span>이나 <span class="orange">< p ></span>, <span class="orange">< h1 ></span> 태그 등을 들 수 있습니다.

<span class="blackbox">한 줄을 차지합니다.</span>

<span class="blackbox">width, height, margin, padding 속성이 모두 반영이 됩니다.</span>

# Display속성 : Inline-block

display 속성이 inline-block으로 지정된 엘리먼트는 기본적으로 inline 엘리먼트처럼 전후 줄바꿈 없이 한 줄에 다른 엘리먼트들과 나란히 배치됩니다.  
하지만 inline 엘리먼트에서 불가능하던 width와 height 속성 지정 및 margin과 padding 속성의 상하 간격 지정이 가능해집니다.
대표적인 inline-block 엘리먼트로 <span class="orange">< button ></span>이나 <span class="orange">< select ></span> 태그 등을 들 수 있습니다.
inline-block 엘리먼트는 명시적으로 헤당 엘리먼트의 스타일을 display: inline-block로 지정해줘야 합니다.

<span class="blackbox">width/height 적용 가능</span>

<span class="blackbox">margin/padding-top/bottom 적용 가능</span>

<span class="blackbox">line-height 적용 가능</span>

\* **고려사항**
inline-block 사이에 공백이 생기게 되는데, parent 태그에 font-size: 0를 적용하면 해결된다.
inline-block 끼리 높이가 안맞을 때 상위 공백이 생기게 되는데 vertical-align: top을 적용하면 해결할 수 있다.

Reference : <https://www.daleseo.com/css-display-inline-block/>
<https://ruden91.github.io/blog/inline-vs-block-vs-inline-block/>
