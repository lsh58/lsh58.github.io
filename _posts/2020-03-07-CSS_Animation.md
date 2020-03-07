---
layout: post
title: "CSS_Animation"
description:
headline:
modified: 2020-03-07
category: webdevelopment
tags: [CSS]
imagefeature:
mathjax:
chart:
share: true
comments: true
featured: true
---

# CSS Animation & Keyframes

CSS3 애니메이션은 요소에 적용되는 CSS 스타일을 다른 CSS 스타일로 부드럽게 전환시켜 줍니다.  
애니메이션은 애니메이션을 나타내는 CSS 스타일과 애니메이션의 중간 상태를 나타내는 키프레임들로 구성되어 집니다. 그리고 애니메이션은 트랜지션보다 훨씬 더 규모가 크고 복잡하며 다양한 능력을 가지고 있기 때문에 좀 더 정밀한 효과를 구현할 수 있습니다.  

### Animation 장점
CSS 애니메이션은 기존에 사용되던 자바스크립트를 이용한 애니메이션보다 다음 세 가지 이유에서 이점을 가집니다.
1. 자바스크립트를 모르더라도 간단하게 애니메이션을 만들 수 있습니다.  
2. 자바스크립트를 이용한 애니메이션은 잘 만들어졌더라도 성능이 좋지 못할때가 있습니다. CSS 애니메이션은 frame-skipping 같은 여러 기술을 이용하여 최대한 부드럽게 렌더링됩니다.  
3. 브라우저는 애니메이션의 성능을 효율적으로 최적화할 수 있습니다. 예를 들어 현재 안보이는 엘리먼트에 대한 애니메이션은 업데이트 주기를 줄여 부하를 최소화할 수 있습니다.  

### Animation 속성
animation 속성도 transition 과 유사하게 단일속성과 속기형으로 작성할 수 있습니다.  
animation 은 위에서 언급했듯이 animation-* 속성과 애니메이션의 중간상태를 정의할 수 있는 @keyframes 으로 구성되어 있습니다.

<span class="orange">animation-name</span>  
애니메이션의 중간 상태를 지정하기 위한 이름을 정의합니다. 중간 상태는 @keyframes 규칙을 이용하여 기술합니다.  
애니메이션 이름을 none 으로 작성하면 애니메이션을 재생하지 않는다.  
설령 none 이라는 이름의 @keyframes 속성이 있어도 애니메이션을 재생하지 않는다.  

<span class="orange">animation-duration</span>  
한 싸이클의 애니메이션이 얼마에 걸쳐 일어날지 지정합니다.  
값을 0이나 음수로 설정하면 애니메이션은 재생되지 않습니다.  

<span class="orange">animation-delay</span>  
엘리먼트가 로드되고 나서 언제 애니메이션이 시작될지 지정합니다.  
0 : 속성을 적용하자마자 애니메이션을 시작한다(기본값).  
now :속성을 적용하자마자 애니메이션을 시작한다. 0으로 설정한 것과 같다. iOS2.0부터 사용할 수 있다.  
숫자와 단위 : 설정한 시간이 지난 뒤에 애니메이션을 시작한다.  
사용할 수 있는 단위는 초(s)와 밀리초 (ms)다. 값이 양수면 속성을 적용한 순간부터 시간을 계산해 애니메이션 재생을 지연한다.  
값이 음수면 속성을 적용한 순간 바로 애니메이션을 실행하지만, 지정한 시간이 지난 뒤의 장면부터 애니메이션을 재생한다.  
예를 들어, 값이 ‘-1s’면 1초가 지난 뒤의 장면부터 애니메이션을 재생한다.

<span class="orange">animation-direction</span>  
애니메이션이 종료되고 다시 처음부터 시작할지 역방향으로 진행할지 지정합니다.  
normal : 애니메이션을 순방향으로 재생한다(기본값). 재생이 한 번 끝나면 첫 번째 프레임부터 다시 시작한다.  
alternate : 순방향으로 애니메이션을 시작해 역방향과 순방향으로 번갈아 애니메이션을 재생한다. 홀수 번째로 재생할 때는 순방향으로 재생하고, 짝수 번째로 재생할 때는 역방향으로 재생한다.  
reverse : 애니메이션을 역방향으로 재생한다. 재생이 한 번 끝나면 마지막 프레임부터 다시 시작한다.  
alternate-reverse : 역방향으로 애니메이션을 시작해 순방향과 역방향으로 번갈아 애니메이션을 재생한다. 홀수 번째로 재생할 때는 역방향으로 재생하고, 짝수 번째로 재생할 때는 순방향으로 재생한다.

<span class="orange">animation-iteration-count</span>  
애니메이션이 몇 번 반복될지 지정합니다. infinite 로 지정하여 무한히 반복할 수 있습니다.  
숫자 : 기본값은 1이며, 설정한 횟수만큼 애니메이션을 재생합니다.  
그리고 숫자가 소수면 애니메이션을 재생하는 도중에 첫 번째 프레임으로 돌아가 멈추고, 숫자가 음수면 애니메이션을 재생하지 않습니다.  
infinite : 애니메이션을 무한으로 반복합니다.  

<span class="orange">animation-play-state</span>  
애니메이션을 멈추거나 다시 시작할 수 있습니다.  
running : 애니메이션을 재생한다(기본값).
paused : 애니메이션을 정지한다.

<span class="orange">animation-timing-function</span>  
중간 상태들의 전환을 어떤 시간간격으로 진행할지 지정합니다.  
ease : cubic-bezier( 0.25, 0.1, 0.25, 1 )과 같습니다.
linear : cubic-bezier( 0, 0, 1, 1 )과 같습니다.
ease-in : cubic-bezier( 0.42, 0, 1, 1 )과 같습니다.
ease-out : cubic-bezier( 0, 0, 0.58, 1 )과 같습니다.
ease-in-out : cubic-bezier( 0.42, 0, 0.58, 1 )과 같습니다.
step-start : steps( 1, start )와 같습니다.
step-end : steps( 1, end )와 같습니다.
steps( n, start|end ) : n단계로 나누어서 변화시킵니다. start 또는 end를 입력하지 않음녀 end로 처리합니다.
cubic-bezier( n, n, n, n ) : n에는 0부터 1까지의 수를 넣습니다.
initial : 기본값으로 설정합니다.
inherit : 부모 요소의 속성값을 상속받습니다.

<span class="orange">animation-fill-mode</span>  
애니메이션이 시작되기 전이나 끝나고 난 후 어떤 값이 적용될지 지정합니다.  
none : 애니메이션이 끝난 후 상태를 설정하지 않습니다.  
forwards : 애니메이션이 끝난 후 그 지점에 그대로 있습니다.  
backwards : 애니메이션이 끝난 후 시작점으로 돌아옵니다.  
both : 애니메이션이의 앞 뒤 결과를 조합하여 설정합니다.  
inherit : 애니메이션의 상태를 상위 요소한테 상속받습니다.  

### @keyframes 과 animation 속기형
애니메이션을 재생할 각 프레임의 스타일을 정의하는 것으로 from 속성이나 0% 속성에 설정한 스타일에서 출발해 to 속성이나 100% 속성에 설정한 스타일로 점차 바뀌면서 애니메이션이 재생됩니다.
키프레임은 애니메이션을 적용할 요소의 animation-name 을 정의하고 그 키프레임 코드 블럭에 재생할 프레임별 시간 비율을 작성합니다.
0% : 애니메이션의 시작 프레임이다.
100% : 애니메이션의 마지막 프레임이다.
from : 애니메이션의 시작 프레임이다. 0% 와 같다.
to : 애니메이션의 마지막 프레임이다. 100% 와 같다.




Reference : [Web Club](https://webclub.tistory.com/621 )
