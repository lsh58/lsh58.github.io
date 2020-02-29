---
layout: post
title: "JS_Hoisting"
description:
headline:
modified: 2020-02-27
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

# 호이스팅(Hoisting)

자바스크립트 함수는 실행되기 전에 함수 안에 필요한 변수값들을 모두 모아서 유효 범위(함수 블록 {} 안에서 유효)의 최상단에 선언한다.  
자바스크립트 Parser가 함수 실행 전 해당 함수를 한 번 훑는다.  
함수 안에 존재하는 변수/함수선언에 대한 정보를 기억하고 있다가 실행시킨다.  

즉, <span class="orange">함수 내에서 아래쪽에 존재하는 내용 중 필요한 값들을 끌어올리는 것이다.</span>  
실제로 코드가 끌어올려지는 건 아니며, 자바스크립트 Parser 내부적으로 끌어올려서 처리하는 것이다.
실제 메모리에서는 변화가 없다.

## 호이스팅의 대상

<span class="orange">var 변수 선언과 함수선언문에서만 호이스팅이 일어난다.</span>(var 변수/함수의 선언만 위로 끌어 올려지며, 할당은 끌어 올려지지 않는다.)<span class="redline"> let/const 변수 선언과 함수표현식에서는 호이스팅이 발생하지 않는다.</span>

호이스팅은 함수선언문과 함수표현식에서 서로 다르게 동작하기 때문에 주의해야 한다.  
변수에 할당된 함수표현식은 끌어 올려지지 않기 때문에 이때는 변수의 스코프 규칙을 그대로 따른다.

<div class="code">
<iframe width="100%" height="300" src="//jsfiddle.net/lsh58/9ztmj0cq/31/embedded/js/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

  **함수선언문과 함수표현식**

<span class="gray">함수선언문 (Function Declaration)</span>  
일반적인 프로그래밍 언어에서의 함수 선언과 비슷한 형식

<span class="gray">함수표현식 (Function Expression)</span>  
변수값에 함수 표현을 담아 놓은 형태  
유연한 자바스크립트 언어의 특징을 활용한 선언 방식  
함수표현식은 익명 함수표현식(함수에 식별자가 주어지지 않는다)과 기명 함수표현식(함수의 식별자가 존재한다)으로 나눌 수 있다. 일반적으로 함수표현식이라고 부르면 앞에 익명이 생략된 형태라고 볼 수 있다.

### 함수표현식의 장점

<span class="orange">클로져로 사용</span>    
<span class="orange">콜백으로 사용(다른 함수의 인자로 넘길 수 있음)</span>

<span class="gray">함수선언문에서의 호이스팅</span>  
함수선언문은 코드를 구현한 위치와 관계없이 자바스크립트의 특징인 호이스팅에 따라 브라우저가 자바스크립트를 해석할 때 맨 위로 끌어 올려진다.

<span class="gray">함수표현식에서의 호이스팅</span>  
함수표현식은 함수선언문과 달리 선언과 호출 순서에 따라서 정상적으로 함수가 실행되지 않을 수 있다.  
함수표현식에서는 선언과 할당의 분리가 발생한다.  

함수표현식의 선언이 호출보다 위에 있는 경우 - 정상 출력  
함수표현식의 선언이 호출보다 아래에 있는 경우 (var 변수에 할당) - TypeError  
함수표현식의 선언이 호출보다 아래에 있는 경우 (const/let 변수에 할당) - ReferenceError  

let/const의 경우, 호이스팅이 일어나지 않기 때문에 위의 예시 그대로 이해하면 된다.
console.log(inner);에서 inner에 대한 선언이 되어있지 않기 때문에 이때는 “inner is not defined” 오류가 발생한다.
함수표현식보다 함수선언문을 더 자주 사용하지만, 어떤 코딩컨벤션에서는 함수표현식을 권장하기도 한다.
즉, 어떤 컨벤션을 갖던지 한가지만 정해서 사용하는 게 좋다.

## 호이스팅 우선순위

<span class="orange">같은 이름의 var 변수 선언과 함수 선언에서의 호이스팅</span> : 변수 선언이 함수 선언보다 위로 끌어올려진다.  
<span class="orange">값이 할당되어 있지 않은 변수의 경우</span> : 함수선언문이 변수를 덮어쓴다.  
<span class="orange">값이 할당되어 있는 변수의 경우</span> : 변수가 함수선언문을 덮어쓴다.  

### TIP 호이스팅 사용 시 주의

<span class="redline">코드의 가독성과 유지보수를 위해 호이스팅이 일어나지 않도록 한다.</span>  
호이스팅을 제대로 모르더라도 함수와 변수를 가급적 코드 상단부에서 선언하면, 호이스팅으로 인한 스코프 꼬임 현상은 방지할 수 있다.
<span class="orange">let/const를 사용한다.</span>  
var를 쓰면 혼란스럽고 쓸모없는 코드가 생길 수 있다. 그럼 왜 var와 호이스팅을 이해해야 할까?
ES6를 어디에서든 쓸 수 있으려면 아직 시간이 더 필요하므로 ES5로 트랜스컴파일을 해야한다.
따라서 아직은 var가 어떻게 동작하는지 이해하고 있어야 한다.

Reference : <https://gmlwjd9405.github.io/2019/04/22/javascript-hoisting.html>