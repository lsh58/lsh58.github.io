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

# JS30_05_Flex Panel Gallery

*초기 코드(Flex Panel Gallery index-START.html)
<div class="code">
<iframe width="100%" height="500" src="//jsfiddle.net/lsh58/em3dya0f/embedded/html,result/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

### 목표
flex panel을 이용해 div 에 변화를 주어보자.

*자바스크립트 코드
<div class="code">
<iframe width="100%" height="500" src="//jsfiddle.net/lsh58/0jxk6wr8/3/embedded/js/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

공부한 내용(CSS)  

<span class="orange">축약형 속성 flex</span>  

보통은 flex-grow, flex-shrink, flex-basis  값을 각각 사용하지 않고 이 세 속성을 한번에 지정하는 flex 축약형을 많이 사용합니다. flex 축약형의 값은 flex-grow, flex-shrink, flex-basis 순서로 지정됩니다.

<span class="gray">flex-grow 속성</span>  
flex-grow값을 양수로 지정하면 flex 항목별로 주축 방향 크기가 flex-basis 값 이상으로 늘어날 수 있게 됩니다. 위의 사진 예시에서 모든 항목의 flex-grow 값을 1로 지정하면 사용가능한 공간은 각 항목에게 동일하게 분배되며, 각 항목은 주축을 따라 분배받은 값만큼 사이즈를 늘려 공간을 차지합니다.

첫 항목의 flex-grow 값을 2로 지정하고 나머지 두 개의 항목을 1로 지정한다면 각 항목에 지정된 flex-grow 값의 비율에 따라 남은 공간이 분배됩니다. 각 항목의 flex-grow 비율이 2:1:1 이므로 첫 항목에게 100 픽셀, 두 번째와 세 번째 항목에게 50 픽셀씩 분배됩니다.

<span class="gray">flex-shrink 속성</span>  
flex-grow 속성이 주축에서 남는 공간을 항목들에게 분배하는 방법을 결정한다면 flex-shrink 속성은 주축의 공간이 부족할때 각 항목의 사이즈를 줄이는 방법을 정의합니다. 만약 flex 컨테이너가 flex 항목을 모두 포함할 만큼 넉넉한 공간을 갖고 있지 않고 flex-shrink 값이 양수이면 flex 항목은 flex-basis에 지정된 크기보다 작아집니다. 또한, flex-grow 속성과 마찬가지로 더 큰 flex-shrink 값을 갖는 항목의 사이즈가 더 빨리 줄어듭니다.

항목의 최소 크기는 실제 축소량을 계산할 때 고려되기 때문에 flex-shrink 속성이 flex-grow 속성에 비해 덜 일관된 모습을 보여줄지도 모릅니다. flex-shrink 속성이 항목의 사이즈를 결정하는 알고리즘에 관해서는 Controlling Ratios of Flex Items on the Main Axis에서 자세히 살펴히보겠습니다.

flex-grow 와 flex-shrink의 값이 비율임을 유의하세요.  flex 항목의 flex 속성을 모두 1 1 200px 로 지정하고 한 항목만 크기가 늘어나는 비율을 타 항목의 두배로 하고 싶으면 해당 flex 항목의 flex 속성을 2 1 200px로 지정하면 되지만, flex 속성 값을 모두  10 1 200px로 지정하고 늘어나는 비율을 두 배로 하고 싶은 항목의 flex 속성 값만 20 1 200px로 지정해도 동일하게 동작합니다.

<span class="gray">flex-basis 속성</span>  
flex-basis 속성은 항목의 크기를 결정합니다. 이 속성의 기본값은 auto이며, 이 경우 브라우저는 항목이 크기를 갖는지 확인합니다. 위의 사진 예시의 경우 항목의 크기가 100 픽셀이므로 flex-basis의 값으로 100 픽셀이 사용됩니다.

flex 항목에 크기가 지정되어 있지 않으면, flex 항목의 내용물 크기가 flex-basis 값으로 사용됩니다. 따라서 flex 컨테이너에서 display: flex 속성만을 지정하면 flex항목들이 각 내용물 크기만큼 공간을 차지하게 됩니다.



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
