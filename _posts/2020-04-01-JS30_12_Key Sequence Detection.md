---
layout: post
title: "JS30_12_Key Sequence Detection"
description:
headline:
modified: 2020-04-01
category: webdevelopment
tags: [JS30]
imagefeature:
mathjax:
chart:
share: true
comments: true
featured: true
---

---

# JS30_12_Key Sequence Detection

### 목표
특정 문자열이 입력되면 반응하게 구현합니다.(console에서)

### 공부한 내용  
```
 pressed.splice(-secretCode.length - 1, pressed.length - secretCode.length);
      if (pressed.join('').includes(secretCode)) {

```
splice()의 첫 번째 파라미터가 음수일 경우, 잘라낼 요소를 뒤에서부터 카운팅한다. -secreteCode.length -1은 배열의 뒤에서부터 secreteCode의 길이만큼을 세고 난 바로 다음 요소부터 잘라낼 것이라는 의미이고, 두 번째 파라미터로 들어가는 pressed.length -secreteCode.length는 pressed와 secrete 두 배열의 차이이기 때문에 첫 번째 파라미터 위치부터 카운팅 했을 경우 pressed 배열의 0번 index까지 가게 된다.

*전체 자바스크립트 코드
<div class="code">
<iframe width="100%" height="300" src="//jsfiddle.net/lsh58/42ukapyv/embedded/html/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

