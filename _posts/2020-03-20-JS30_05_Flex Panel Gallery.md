---
layout: post
title: "JS30_05_Flex Panel Gallery"
description:
headline:
modified: 2020-03-20
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

# JS30_04_Array Cardio Day 1

*초기 코드(CSS Variables index-START.html)
<div class="code">
<iframe width="100%" height="300" src="//jsfiddle.net/lsh58/0jxk6wr8/embedded/html/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

### 목표
배열에 대해 공부합니다.

*자바스크립트 코드
<div class="code">
<iframe width="100%" height="500" src="//jsfiddle.net/lsh58/0jxk6wr8/3/embedded/js/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

공부한 내용  

<span class="orange">filter(callback함수)</span>  

 - arr.filter(callback[thisArg]) 의 형태 입니다.  
 - 배열에 조건을 주어 조건에 부합하는 원소들을 찾아냅니다.  

사용 예) arr.filter( function(a){ return a>0 });  

<span class="orange">화살표함수</span>  


<div class="code">
<iframe width="100%" height="300" src="//jsfiddle.net/lsh58/0jxk6wr8/3/embedded/js/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

1. 함수표현의 간략화  
function 키워드를 생략할 수 있습니다.  
함수의 매개변수가 1개라면 괄호()를 생략할 수 있습니다.  
함수 바디가 표현식 하나라면 중괄호와 return 문을 생략할 수 있습니다.  

2. 화살표 함수는 항상 익명함수입니다.  

3. 화살표 함수는 this가 정적으로 묶입니다.  

4. 객체 생성자로 사용할 수 없습니다.  

5.  arguments 변수를 사용할 수 없습니다.  

<span class="orange">map(callback함수)</span>  
 - arr.map(callback[thisArg]) 의 형태 입니다.  
 - 어떠한 배열에 특정 규칙을 적용시켜 새로운 배열을 만든다.  

<span class="orange">템플릿 리터럴</span>  
`${value}`템플릿 리터럴의 ${} 표현식 은 처리된 값을 문자열로 반환한다.  

<span class="orange">sort(compareFunction(a, b))</span>  
인자로 받는 함수는 직접적으로 정렬 순서를 결정하는데 사용되는 함수입니다.  
이를 생략하면 유니코드 순으로 정렬됩니다.  
compare function을 넣어준다면, 다음과 같은 원리로 정렬 순서가 결정됩니다.  

compareFunction(a, b)이 <span class="gray">0보다 작은 경우</span> <span class="redline">a를 b보다 낮은 색인으로 정렬합니다.
즉, a가 먼저옵니다.</span>  
compareFunction(a, b)이 <span class="gray">0을 반환하면</span> <span class="redline">a와 b의 순서를 변경하지 않습니다.</span>  
compareFunction(a, b)이 <span class="gray">0보다 큰 경우</span> <span class="redline">b를 a보다 낮은 색인으로 정렬합니다.
즉, b가 먼저옵니다.</span>  

사용 예) arr.sort ( function(a,b){ if(a>b){return 1;} else{Return -1;});

<span class="orange">reduce(callback함수,초기값)</span>  
Reduce 메서드는 배열에 대하여 주어진 리듀서(reducer)함수를 실행하고 결과 값을 반환합니다.  

사용 예) arr.reduce ( function(total,a){return total+a;},0});

배열의 각 요소가 주어진 콜백함수를 거치게 됩니다. 이 콜백함수를 리듀서(reducer) 라고 합니다.  
초기값은 최초의 리듀서 호출에서 accumulator(누산기)에 제공하는 값입니다. 초기값이 없다면 배열의 첫번째 요소(0번 인덱스)를 사용하고 초기값이 있다면 주어진 초기값을 사용합니다. reduce()의 반환값은 각 요소가 리듀서를 거쳐 누적된 값의 결과 값입니다.  
