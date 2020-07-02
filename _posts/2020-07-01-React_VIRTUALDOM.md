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
  
  
  
# 버츄얼돔은 왜 좋은가. 어떻게 동작하는가. JQUERY의 돔직접참조에 비해서 무엇이 개선되었는가.


<span class="orange">변수의 사용</span>


Reference : <https://ryublock.tistory.com/41>
<https://velog.io/@denny6389/React-%EA%B8%B0%EC%88%A0-%EB%AC%B8%EC%A0%9C>
<https://hashnode.com/post/the-one-thing-that-no-one-properly-explains-about-react-why-virtual-dom-cisczhfj41bmssp53mvfwmgrq>