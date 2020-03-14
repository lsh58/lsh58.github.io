---
layout: post
title: "CSS_Naming-BEM"
description:
headline:
modified: 2020-03-14
category: webdevelopment
tags: [CSS]
imagefeature:
mathjax:
chart:
share: true
comments: true
featured: true
---

# 디버깅 시간을 절약 할 수있는 CSS 명명 규칙

id, class명을 작성할때, 항상 고민이였던 부분이 네이밍이였고, 그때그때 떠오르는데로 작성하는 경우가 많았다. 그러다 보니 나중에 이게 어떤놈인지 알기 힘들었고 수정하려면 HTML과 CSS를 다 찾아보아야 했습니다.

CSS 명명 규칙을 통해 해결하려고하는 세 가지는 다음과 같습니다.  
selector가 무엇을 하는지는 이름만 보고 알 수 있습니다.   
selector를 보기만 해도 어디에 사용할 수 있는지 알 수 있습니다.  
클래스 이름 간의 관계를 알기 위해서는 클래스 이름을 살펴 보기만 해도 됩니다.  

# BEM

BEM은 기본적으로 ID를 사용하지 않으며, class만을 사용합니다.  
또, '어떻게 보이는가'가 아니라 '어떤 목적인가'에 따라 이름을 짓습니다. 예를 들어, 에러 메시지를 띄우는 P 태그에게는 .red가 아닌, .error라는 이름을 줘야합니다.
이름을 연결할 때는 block-name과 같이 하이픈 하나만 써서 연결합니다

### 작명규칙(Naming Convention)

>개발, 디버깅, 유지보수를 위하여 CSS 선택자의 이름을 가능한 한 명확하게 만드는 것이 목표입니다.
>소문자, 숫자 만을 이용해서 작명합니다.
>여러단어의 조합은 하이픈(-)으로 연결하여 작명합니다.

BEM은 전체 사용자 인터페이스를 작은 재사용 가능한 구성 요소(components)로 분할하려고 시도합니다.

BEM은 <span class="orange">Blcok</span>, <span class="orange">Element</span>, <span class="orange">Modifier</span>를 뜻합니다. 이 세가지 요소를 이용해 이름을 짓고 각각 __와 --로 구분합니다. 



![image](https://github.com/lsh58/lsh58.github.io/blob/master/images/post/03.png?raw=true)

### Block

> .stick-man { }

BEM의 B는 'Block'을 의미합니다.  
스틱 맨은 디자인 블록과 같은 구성 요소(component)를 나타냅니다.

블록 = 재사용 가능한 기능적으로 독립적인 페이지 컴포넌트(A functionally independent page component that can be reused)  
실제 세계에서 이 'block'은 사이트 navigation, header, footer 또는 다른 디자인 블록을 나타낼 수 있습니다.  
위에서 설명한 연습에 따라이 구성 요소(component)의 이상적인 클래스 이름은 stick-man입니다.  
구성 요소(component)는 다음과 같이 스타일을 지정해야합니다.  

재사용 할 수있는 기능적으로 독립적인 페이지 구성 요소. HTML에서 블록은 class 속성으로 표시됩니다.  
형태(red, big)가 아닌 목적(menu, button)에 맞게 결정해야 합니다.  
블록은 환경에 영향을 받지 않아야 한다. 즉, 여백이나 위치를 설정하면 안됩니다.  
태그, id 선택자를 사용하면 안됩니다.  
블록은 서로 중첩해서 작성 할 수 있습니다.  
예) header, menu, search-form ….



![image](https://github.com/lsh58/lsh58.github.io/blob/master/images/post/04.png?raw=true)

### Element

>.stick-man__head {}
>.stick-man__arms {}
>.stick-man__feet {}

'BEM'의 E는 요소(Elements)를 나타냅니다.  
예를 들어, 스틱 맨은 head한 개, arms이 두 개, feet이 두 개 있습니다.  
head, feet 및 arms은 구성 요소(component) 내의 모든 요소(elements)입니다.  
그것들은 하위 구성 요소(child components), 즉 전체 상위 구성 요소(parent component)의 하위 구성 요소((child components))로 볼 수 있습니다.  

BEM 명명 규칙을 사용하면 요소(element) 이름 뒤에 2 개의 밑줄(two underscores)을 추가하여 요소(element) 클래스 이름을 파생시킵니다.  
엘리먼트(요소)는 블럭을 구성하는 단위입니다. 블럭이 뭔가 뚝 떼서 쓸 수 있는 독립적인 형태라면, 요소는 의존적인 형태입니다. 자신이 속한 블럭 내에서만 의미를 가지죠.  

형태(red, big)가 아닌 목적(item, text, title)에 맞게 결정해야 합니다.  
요소는 중첩해서 작성 할 수 있습니다.  
요소는 블록의 부분으로만 사용 할 수 있고 다른 요소의 부분으로 사용할 수 없습니다.  
모든 블록에서 요소는 필수가 아닌 선택적으로 사용한다. 즉 블록안에 요소가 없을 수도 있습니다.  
예) menu__item, header__title …

![image](https://github.com/lsh58/lsh58.github.io/blob/master/images/post/05.png?raw=true)

### Modifier

>.stick-man--blue {}
>.stick-man--red {}

'BEM'의 M은 수정(Modifiers)의 약자입니다.  
stick- man이 수정되고 blue 또는 red stick- man을 가질 수 있다면 어떨까요?  
현실 세계에서는 red 단추 또는 blue 단추가 될 수 있습니다. 이것들은 해당 구성 요소(component)의 수정(modifications)입니다.  

BEM을 사용하면 수정(modifier) 클래스 이름은 요소(element) 이름 옆에 하이픈(hyphens) 두 개를 추가하여 파생됩니다.  
블록이나 요소의 모양(color, size..), 상태(disabled, checked..)를 정의합니다.  
수식어의 블리언 타입과 키-벨류 타입이 있습니다.  
블리언 타입 : 수식어가 있으면 값이 true 라고 가정합니다. (form__button — disabled)  
키-벨류 타입 : 키, 벨류를 하이픈으로 연결하여 표시합니다. (color-red, theme-ocean)  
수식어는 단독으로 사용할 수 없다. 즉 기본 블록과 요소에 추가하여 사용해야 합니다. ( class=”block__element block__element — modifier”)

### 클래스명 수정으로부터 JS연결을 보호하는 방법

#### 1.js- 클래스 이름 사용

이러한 버그를 완화하는 한 가지 방법은 문제의 DOM 요소(element)와의 관계를 나타 내기 위해 js-* 클래스 이름을 사용하는 것입니다.
> <div class="site-navigation js-site-navigation"></div>

규약에 따라js-site-navigation 클래스 이름을 보는 사람은 JavaScript 코드에서 DOM 요소(element)와 관계가 있음을 이해합니다.

#### 2.Rel 속성(attribute) 사용
기본적으로 rel 속성(attribute)은 링크 된 자원이 참조하는 문서와의 관계를 정의합니다.
> <div class="site-navigation" rel="js-site-navigation"></div>
> const nav = document.querySelector("[rel='js-site-navigation']")

#### 보너스 팁 : CSS 코멘트 추가 작성
이것은 명명 규칙과는 아무런 관련이 없지만 시간을 절약 할 수 있습니다.
많은 웹 개발자가 자바 스크립트 주석을 쓰지 않거나 몇 가지를 고집하지는 않지만 더 많은 CSS 주석을 작성해야한다고 생각합니다.
CSS가 가장 우아한 "언어"가 아니기 때문에 잘 구성된 코드는 코드를 이해하려고 할 때 시간을 절약 할 수 있습니다.

### 이점

SASS의 부모참조자(&)와 같이쓰면 아주 좋습니다. 작성된 SASS에서 요소를 쉽게 찾을 수 있습니다.
예를 들어, .header 아래에 &__logo, &__search로 작성하기 때문에 "아, 저게 헤더 아래 로고고 저건 헤더 아래 검색이구나"란 걸 바로 알 수가 있습니다.
> .header {
>   &__nav {
>      position: absolute;
>   }
>   &__list {
>      clor: red;
>   }

### 단점
클래스네임이 너무 길어서 HTML 마크업이 한눈에 들어오지 않는다는 단점이 있습니다.
특히 스크립트로 modifier를 변경해야할 때, classList.add("block-name__element-name--modifier")처럼 길게 길게 작성해야하는 건 불편해보입니다.
하이픈과 언더바가 혼재되어 있어, 더블클릭해서 클래스네임을 선택할때 한 번에 선택이 안 됩니다.

Reference : [스키머(schemr)](https://medium.com/witinweb/css-%EB%B0%A9%EB%B2%95%EB%A1%A0-1-bem-block-element-modifier-1c03034e65a1)
[Early adopter 의 디자인 번역 공장](https://www.vobour.com/-css-%EB%94%94%EB%B2%84%EA%B9%85-%EC%8B%9C%EA%B0%84%EC%9D%84-%EC%A0%88%EC%95%BD-%ED%95%A0-%EC%88%98%EC%9E%88%EB%8A%94-css-%EB%AA%85%EB%AA%85-%EA%B7%9C%EC%B9%99)