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

### 공부한 내용(CSS)  

<span class="orange">축약형 속성 flex</span>  

flex 항목에 적용할 수 있는 속성은 다음과 같습니다.

- flex-grow
- flex-shrink
- flex-basis

500 픽셀의 크기를 갖는 flex 컨테이너 내에 100 픽셀 크기의 자식 세 개가 존재할 때, 사용가능한 공간 200 픽셀이 남게 됩니다. 기본적으로 flexbox는 이 공간을 마지막 자식 요소 다음에 빈공간으로 남겨둡니다.위의 세 가지 속성을 변경한다는 것은 flex 항목에게 사용가능한 공간을 분배하는 방식을 변경하는 것입니다. 사용가능한 공간 개념은 flex 항목을 정렬할 때 특히 중요합니다.  
보통은 flex-grow, flex-shrink, flex-basis  값을 각각 사용하지 않고 이 세 속성을 한번에 지정하는 flex 축약형을 많이 사용합니다. flex 축약형의 값은 flex-grow, flex-shrink, flex-basis 순서로 지정됩니다.

<span class="gray">flex-grow 속성</span>  
flex-grow값을 양수로 지정하면 flex 항목별로 주축 방향 크기가 flex-basis 값 이상으로 늘어날 수 있게 됩니다. 위의 사진 예시에서 모든 항목의 flex-grow 값을 1로 지정하면 사용가능한 공간은 각 항목에게 동일하게 분배되며, 각 항목은 주축을 따라 분배받은 값만큼 사이즈를 늘려 공간을 차지합니다.

첫 항목의 flex-grow 값을 2로 지정하고 나머지 두 개의 항목을 1로 지정한다면 각 항목에 지정된 flex-grow 값의 비율에 따라 남은 공간이 분배됩니다. 각 항목의 flex-grow 비율이 2:1:1 이므로 첫 항목에게 100 픽셀, 두 번째와 세 번째 항목에게 50 픽셀씩 분배됩니다.

**알아낸것**
flex-grow를 쓰려면,
1. 부모의 사이즈가 없어야한다.
2. 각각 사이즈를 가지고 있지 않은 상태여야 각각 가진 flex-grow의 비율대로 사이즈가 자동으로 조절된다.
3. 만약 각각 사이즈를 갖고 있다면, 각각의 사이즈를 차지하고 남은 공간을 flex-gorw의 비율대로 가져간다.
4. 만약 flex-grow가 0인값이 있다면, 사이즈를 못잡아야 하지만, 속에 내용이 있다면 그 크기만큼 사이즈를 차지한다.


<span class="gray">flex-shrink 속성</span>  
flex-grow 속성이 주축에서 남는 공간을 항목들에게 분배하는 방법을 결정한다면 flex-shrink 속성은 주축의 공간이 부족할때 각 항목의 사이즈를 줄이는 방법을 정의합니다. 만약 flex 컨테이너가 flex 항목을 모두 포함할 만큼 넉넉한 공간을 갖고 있지 않고 flex-shrink 값이 양수이면 flex 항목은 flex-basis에 지정된 크기보다 작아집니다. 또한, flex-grow 속성과 마찬가지로 더 큰 flex-shrink 값을 갖는 항목의 사이즈가 더 빨리 줄어듭니다.

항목의 최소 크기는 실제 축소량을 계산할 때 고려되기 때문에 flex-shrink 속성이 flex-grow 속성에 비해 덜 일관된 모습을 보여줄지도 모릅니다. flex-shrink 속성이 항목의 사이즈를 결정하는 알고리즘에 관해서는 Controlling Ratios of Flex Items on the Main Axis에서 자세히 살펴히보겠습니다.

flex-grow 와 flex-shrink의 값이 비율임을 유의하세요.  flex 항목의 flex 속성을 모두 1 1 200px 로 지정하고 한 항목만 크기가 늘어나는 비율을 타 항목의 두배로 하고 싶으면 해당 flex 항목의 flex 속성을 2 1 200px로 지정하면 되지만, flex 속성 값을 모두  10 1 200px로 지정하고 늘어나는 비율을 두 배로 하고 싶은 항목의 flex 속성 값만 20 1 200px로 지정해도 동일하게 동작합니다.

**알아낸것**
flex-shrink를 쓰려면,
1. 부모의 사이즈가 없어야한다 ( flex-grow와 동일)
2. 각각 사이즈가 없다면, 특정요소에만 shrink를 줘도 변하는것이 없다.
3. 각각 사이즈가 있다면, flex-shrink를 0을 갖는 요소는 나머지 요소들(flex-shrink값이 1인 요소들)이 다 줄어들때까지 사이즈가 줄어들지 않는다.


<span class="gray">flex-basis 속성</span>  
flex-basis 속성은 항목의 크기를 결정합니다. 이 속성의 기본값은 auto이며, 이 경우 브라우저는 항목이 크기를 갖는지 확인합니다. 위의 사진 예시의 경우 항목의 크기가 100 픽셀이므로 flex-basis의 값으로 100 픽셀이 사용됩니다.

flex 항목에 크기가 지정되어 있지 않으면, flex 항목의 내용물 크기가 flex-basis 값으로 사용됩니다. 따라서 flex 컨테이너에서 display: flex 속성만을 지정하면 flex항목들이 각 내용물 크기만큼 공간을 차지하게 됩니다.


*자바스크립트 코드
<div class="code">
<iframe width="100%" height="500" src="//jsfiddle.net/lsh58/0jxk6wr8/3/embedded/js/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>
