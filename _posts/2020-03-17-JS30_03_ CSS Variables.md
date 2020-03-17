---
layout: post
title: "JS30_03_CSS Variables"
description:
headline:
modified: 2020-03-17
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

# JS30_03_CSS Variables

![image](https://github.com/lsh58/lsh58.github.io/blob/master/images/post/js30/j30-03_01.PNG?raw=true)

*초기 코드(CSS Variables index-START.html)
<div class="code">
<iframe width="100%" height="300" src="//jsfiddle.net/lsh58/bcLrt80h/embedded/html,result/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

### 목표
Spacing과 blur, 색상표가 작동되도록 만듭니다.

공부한 내용  

<span class="orange">:root</span>  

```  
   :root {
      --base: #ffc600;
      --spacing: 10px;
      --blur: 10px;
    }

```

:root 가상선택자는 문서 트리의 루트 요소(가장상위단계의 요소)를 선택합니다.  
:root에서는 --로 시작을 하며, 뒤에 나오는 부분은 변수명을 입력하시면 되는데, 변수명의 규칙은 CSS에서 클래스명이나 아이디명을 짓는 것과 같습니다. 예시에서는 div-main-color 라고 했지만 그냥 divMainColor 라고 하셔도 됩니다. 자신이 쉽게 알아볼 수 있도록 이름을 지어주시면 됩니다.
```
    img {
      padding: var(--spacing);
      background: var(--base);
      filter: blur(var(--blur));
    }
    .hl {
      color: var(--base);
    }

```
그리고 적용시켜야 할 선택자의 스타일에는 var로 변수를 선언해 주며, 소괄호를 넣어주고, 해당 소괄호 안쪽에 root 부분과 마찬가지로 --를 먼저 넣고 뒤에 동일한 
변수명을 입력하시면 됩니다. 마무리는 세미콜론을 꼭 잊지 마시기 바랍니다.

*자바스크립트 코드
<div class="code">
<iframe width="100%" height="300" src="//jsfiddle.net/lsh58/bcLrt80h/2/embedded/js/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

<span class="orange">Date()</span>  

const suffix = this.dataset.sizing || '';
//dataset.sizing이 없는 input이 있으므로 없을때는 공백을 넣도록 설정

document.documentElement.style.setProperty(`--${this.name}`, this.value + suffix); 
//이벤트가 일어난 요소의 name값 (ex.spacing) 의 값을 해당요소의 value값 + suffix값으로 설정해준다.
