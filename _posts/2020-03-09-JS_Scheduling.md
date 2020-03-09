---
layout: post
title: "JS_Scheduling"
description:
headline:
modified: 2020-03-09
category: webdevelopment
tags: [JS]
imagefeature:
mathjax:
chart:
share: true
comments: true
featured: true
---

---

# Scheduling : setTimeout 과 setInterval

일정 시간이 지난 후에 원하는 함수를 예약 실행(호출)할 수 있게 하는 것을 "호출 스케줄링(scheduling a call)"이라고 합니다.  
호출 스케줄링을 구현하는 방법은 두 가지가 있습니다.  
<span class="orange">setTimeout을 이용해 일정 시간이 지난 후에 함수를 실행하는 방법</span>  
<span class="orange">setInterval을 이용해 일정 시간 간격을 두고 함수를 실행하는 방법</span>  
자바스크립트 명세서엔 setTimeout과 setInterval가 명시되어있지 않습니다. 하지만 시중에 나와있는 모든 브라우저, Node.js를 포함한 자바스크립트 호스트 환경 대부분이 이와 유사한 메서드와 내부 스케줄러를 지원합니다.  

### setTimeout

>let timerId = setTimeout(func|code, [delay], [arg1], [arg2], ...)

<span class="gray">func|code</span>  
실행하고자 하는 코드로, 함수 또는 문자열 형태입니다. 대게는 이 자리에 함수가 들어갑니다. 하위 호환성을 위해 문자열도 받을 수 있게 해놓았지만, 추천하진 않습니다.  
<span class="gray">delay</span>  
실행 전 대기 시간(지연 간격)으로, 단위는 밀리초(millisecond, 1000밀리초 = 1초)입니다. 기본값은 0입니다.  
<span class="gray">arg1, arg2…</span>  
함수에 전달할 인수들로, IE9 이하에선 지원하지 않습니다.  

### setInterval

>let timerId = setInterval(func|code, [delay], [arg1], [arg2], ...)

setInterval 메서드는 setTimeout과 동일한 문법을 사용합니다.  
인수 역시 동일합니다. 다만, setTimeout이 함수를 단 한 번만 실행하는 것과 달리 setInterval은 함수를 주기적으로 실행하게 만듭니다.  
함수 호출을 중단하려면 clearInterval(timerId)을 사용하면 됩니다.



Reference : <https://ko.javascript.info/settimeout-setinterval#tasks>
