---
layout: post
title: "VIRTUALDOM"
description:
headline:
modified: 2020-07-01
category: webdevelopment
tags: [REACT]
imagefeature:
mathjax:
chart:
share: true
comments: true
featured: true
---

---

# REALDOM VS VIRTUALDOM  
  
### Real DOM = DOM (Document Object Model)  

HTML문서를 프로그래밍적으로 접근 가능하게 해주는 인터페이스이다.  
HTML 파일이 브라우저에 표현되는 과정(랜더링)을 살펴보면 다음과 같은데,  

1) 웹 문서(HTML파일)를 로드 한다.  
2) 웹 문서를 브라우저가 이해할 수 있는 구조로 구성하여 메모리에 올린다.  
3) 그리고 브라우저는 브라우저가 이해할 수 있는 구조를 그려낸다.  

이때 브라우저의 랜더링 엔진이 모든 요소(Element)와 속성(Attribute)등을 각각의 객체로 만들고 이것을 트리 구조로 구성하는데, 이를 DOM이라고 한다.  

DOM의 동작과정을 살펴보면 다음과 같다.  

1) DOM Tree 생성 - 브라우저가 전달 받은 HTML DOM으로 변환  
2) Render Tree 생성 - css 등 스타일 요소 attach DOM Tree와 같게 Render Tree 생성  
3) Layout - 각 노드들이 어디에 나타야할지 스크린 좌표 계산  
4) Paint - 랜더링 된 요소에 색을 입히는 과정  

Element를 추가, 수정, 생성 하면서 DOM이 수정 되면 Render Tree생성, Layout 생성, Paint가 다시 이루어지는데, 이는 리소스가 변경 될 때마다 전체 페이지를 갱신 시킨다고 생각하면 된다.  복잡한 SPA(싱글 페이지 어플리케이션) 에서는 DOM 조작이 많이 발생하는데, 그 뜻은 그 변화를 적용하기 위해 브라우저가 많이 연산을 해야한단 소리고, 전체적인 프로세스를 비효율적으로 만든다는 것이다. 이를 해결하기 위해 생겨난 개념이 Virtual DOM이다.  
  
### Virtual DOM
말 그대로 가상의 DOM이다. 변화가 일어나면, 실제로 브라우저의 DOM 에 새로운걸 넣는것이 아니라, 자바스크립트로 이뤄진 가상 DOM 에 한번 렌더링을 하고, 기존의 DOM 과 비교를 한 다음에 정말 변화가 필요한 곳에만 업데이트를 해주는 것. 즉, 데이터가 바뀌었을 때 어떻게 업데이트를 할 지를 고려하는 것이 아닌, 일단 바뀐 데이터로 그려놓고 비교를 한 다음, 바뀐 부분만 바꾸는 것이다.  
  
  

# 버츄얼돔은 왜 좋은가. 어떻게 동작하는가.
  
Virtual DOM 을 사용하면, 실제 DOM 에 접근하여 조작하는 대신에, 이를 추상화 시킨 스크립트 객체(DOM의 사본)를 구성하여 사용한다. React 에서 데이터가 변하여 브라우저상의 실제 DOM 을 업데이트 할 때에는 다음과 같이 3가지 절차를 밟는다.  
  
1) 데이터가 업데이트되면, 전체 UI 를 Virtual DOM 에 리렌더링 한다.  
2) 이전 Virtual DOM 에 있던 내용과 현재의 내용을 비교한다.  
3) 바뀐 부분만 실제 DOM 에 적용이 된다.  
  
jQuery의 DOM 조작 메서드는 신이 내린 선물이었고, 요상하기 그지 없는 DOM을 다루는 고통을 완화하는 데에 도움을 주었지만, 그 밑에 깔린 퍼포먼스 문제를 전혀 해결하지 않았다. 모바일이 대세인 웹 브라우징 환경에 우리가 대응하게 되면서, 느린 UI 상호작용은 빈번해졌고 훨씬 두드러지게 되었다.  

우리는 대부분의 경우 단일 페이지 웹 앱(SPA)과 제3자 외부 컨텐츠가 넘쳐나는 페이지들을 만든다. 이 경우, 첫 렌더링 이후에 아주 느린 성능을 보인다. 페이지마다 천개가 넘는 DOM 요소를 조작하고, 페이지에 온갖 HTML 요소를 비동기적으로 불러온 뒤 그것들에 스타일을 적용해야만 한다. 이제 더 이상은 간단한 HTML 문서가 아니게 되어버렸고, 아주 느린 UX가 발생하게 되는 것이다. 모든 자원이 다운로드되고 나면, 단지 DOM 요소를 재배치하거나, 컨텐츠를 업데이트하는 정도의 작업만 수행할 뿐인데, 왜 이렇게 느려지는 것일까? 이 문제의 가장 큰 원인은 바로 유명 라이브러리들의 DOM 조작 메서드가 아주 느리다는 점이다.  

가상 DOM 라이브러리들은 거대한 UI 전체를 항상 다시 렌더링하는 것을 원칙으로 둔다. 훨씬 빠르고 유지보수가 용이한 웹 UI를 만든다는 목표를 충족시키기 위하여, 가장 빠른 DOM 조작들만 허용하고, 이러한 DOM 조작마저도 반드시 라이브러리 자체에 의한 명령을 통하여서만 이루어지도록 하는 것이다. 가상 DOM에 대한 이러한 떠오르는 접근 방식은 단순히 DOM 조작을 일괄 처리하는 것을 능가한다. 또한 이는 HTML Templating에 견주어 보아도 대부분의 경우 이를 능가한다. 이 라이브러리들은 대개 선언적인 객체 추상화(Declarative Object Abstractions)를 통하여 UI 코드 덩어리들을 다룬다. 이러한 추상물은 보통 컴포넌트라고 불린다.  

객체 추상화 : 객체들의 공통적인 프로퍼티(이름, 값)와 메서드(클래스나 객체에 숙해 있는 함수)를 뽑아내는 작업. 코드상에서 구현(로직) 부분을 제외한 오직 선언 부분만을 설계하는 것을 말한다.  

프레임워크에 의하여 별도로 정의된 컴포넌트 객체 덩어리의 전/후 변화를 비교(diff), 그리고 반드시 필요할 때에만 변화 내용을 DOM에 기록하기. 이런 접근법을 통하여 가상 DOM 접근법은 성능뿐만 아니라 유지보수성까지 향상시킨다고 증명되었다.

![image](https://github.com/lsh58/lsh58.github.io/blob/master/images/post/React/virtualdom01.png?raw=true)


Reference : <https://ryublock.tistory.com/41>
<https://velog.io/@denny6389/React-%EA%B8%B0%EC%88%A0-%EB%AC%B8%EC%A0%9C>
<https://hashnode.com/post/the-one-thing-that-no-one-properly-explains-about-react-why-virtual-dom-cisczhfj41bmssp53mvfwmgrq>