---
layout: post
title: "JS30_02_JS and CSS clock"
description:
headline:
modified: 2020-03-16
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

# JS30_02_JS and CSS clock

![image](https://github.com/lsh58/lsh58.github.io/blob/master/images/post/js30/j30-02_01.PNG?raw=true)

*초기 코드(JS and CSS clock index-START.html)
<div class="code">
<iframe width="100%" height="300" src="//jsfiddle.net/lsh58/o01zvauy/embedded/html,result/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

### 목표
현재 시간을 아날로그 시계로 구현시킵니다.

공부한 내용  
<span class="orange">transition-timing-function</span>  
transition-timing-function 속성은 요소의 움직임 기능을 정의합니다.  
<span class="gray">linear</span>	처음 속도와 마지막 속도가 일정합니다.  
<span class="gray">ease</span>	처음엔 천천히 시작하여 빨라지고 마지막에 다시 느려집니다.  
<span class="gray">ease-in</span>	천천히 시작되어 정상 속도가 됩니다.  
<span class="gray">ease-out</span>	마지막에 천천히 속도를 줄여 끝납니다.  
<span class="gray">ease-in-out</span>	천천히 시작되어 정상 속도가 되었다가 마지막에 느려집니다.  
<span class="gray">step-start</span>	애니메이션을 시작점에서만 표현됩니다.  
<span class="gray">step-end</span>	애니메이션을 끝점에서만 표현됩니다.  
<span class="gray">steps(int,start|end)</span>	애니메이션을 단계별로 설정합니다.  
<span class="gray">cubic-bezier(n,n,n,n)</span>	베지어 곡선값을 만들어서 속도를 설정합니다.  
<span class="gray">inherit</span>	transition-timing-function의 속성 값을 상위요소한테 상속받습니다.  


*자바스크립트 코드
<div class="code">
<iframe width="100%" height="300" src="//jsfiddle.net/lsh58/o01zvauy/3/embedded/js/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

<span class="orange">Date()</span>  
현재 시간정보를 가져옵니다.  
getSeconds();  현재 초  
getMinutes();  현재 분  
getHours();    현재 시간  

<span class="orange">1초당 움직일 각도구하기</span>  
초 : ((현재 초 / 60) * 360 )   + 90  
분 : ((현재 분 / 60) * 360 )  +  ((현재 초 / 60) * 6)   + 90  
시간 : ((현재 시간 / 60) * 360 ) + ((현재 분 / 60) * 30) + 90  

