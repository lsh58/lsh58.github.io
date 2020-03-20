---
layout: post
title: "CSS_Naming-OOCSS"
description:
headline:
modified: 2020-03-17
category: webdevelopment
tags: [CSS]
imagefeature:
mathjax:
chart:
share: true
comments: true
featured: true
---

---

# OOCSS
## Object Oriented Cascading Style Sheets
CSS를 모듈 방식으로 코딩하여 중복을 최소화하는 기법  

## 주요원리
<span class="redline">구조와 외양을 분리하자.</span>  
외양(skin)으로 분리시켜, 결합시키면 다양한 결과물을 얻을 수 있음.  
```
.button {
   ...
}
.box {
   ...
}
.widget {
   ...
}
```

<span class="redline">컨테이너와 컨텐츠를 분리하자.  </span>  

```
.header-inside{
   position:relative;
   margin:0 auto;
   width:980px;
   height:260px;
   padding:20px;
   overflow:hidden;
}
```
  
다른 영역에서도 사용가능하도록 .header-inside라는 속성으로 추출(분리)하면,  
중복 코드를 사용하게 되는 경우가 적어진다.


## 명명방법
<span class="orange">간결함</span>: 되도록 짧게  
<span class="orange">명료함</span>: 스타일과 작동 방식이 고스란히 드러나게 분명한 말뜻(Semantics): 어떻게 생겼는지가 아니라, 어떤 모듈인지  
<span class="orange">포괄성</span>: 대부분의 사이트에서도 적용되도록  
<span class="orange">화면 중심성</span>: 종이나 다른 매체가 아닌 모니터를 기준으로  

```
//일반적인 명명법
.twitterbtn {
  border:3px solid #000;
  padding:10px 20px;
  color:#fff;
  border-radius:10px;
  background:red;
}
.facebookbtn {
  border:3px solid #000;
  padding:10px 20px;
  color:#fff;
  border-radius:10px;
  background:gray;
}
```

```
//OOCSS로 정리하면
.btnbase {
  border:3px solid #000;
  padding:10px 20px;
  color:#fff;
  border-radius:10px;
}
.twitter {
  background:red;
}
.facebook {
  background:gray;
}
```

## OOCSS의 장점
코드의 재사용성  
코드 재사용으로 인한 스타일시트의 용량 축소  
스타일시트의 용량 축소로 인한 속도 향상  

## OOCSS의 단점
다중 클래스 사용으로 HTML가 복잡해짐  
non-semantic한 클래스 사용  
<span class="redline">Sass와 함께 사용하게 되면 단점을 보완할 수 있음</span> 

Sass의 <span class="gray">mixin</span>, <span class="gray">extend</span> 방식을 사용하면 Semantic한 HTML코드를 얻을 수 있다. (두 방법의 HTML코드는 동일함)
```
@mixin btnbase{
  border:3px solid #000;
  padding:10px 20px;
  color:#fff;
  border-radius:10px;
}
.twitterbtn {
  @include btnbase;
  background:red;
}
.facebookbtn {
  @include btnbase;
  background:gray;
}
```

```
.btnbase{
  border:3px solid #000;
  padding:10px 20px;
  color:#fff;
  border-radius:10px;
}
.twitterbtn {
  @extend .btnbase;
  background:red;
}
.facebookbtn {
  @extend .btnbase;
  background:gray;
}
```
mixin방식으로 했을 경우는 컴파일시에 중복된 코드가 발생하므로,  
extend방식으로 하는 것이 더 좋다.  
***  
참고<https://tech.bellycard.com/blog/sass-mixins-vs-extends-the-data/>  
중복코드가 나쁜 주된 이유는 유지보수가 힘들기 때문인데, mixin의 경우 사람이 만지는 단계에서는 중복이 발생하지 않으므로 유지보수의 문제가 발생하지 않습니다. 또한 중복이 발생하더라도 그것이 기계가 해석하기 더 쉬운 형태라면 성능이 좋아질 것입니다. 따라서 단순히 컴파일 후 중복이 더 많이 발생한다고 해서 나쁘다고 평가하는 것은 틀린 판단입니다.   
extend의 단점: CSS 순서를 바꾼다. 연관없는 선택자를 함께 묶는다. 원하는 것만 수정하지 못하는 경우가 생기고, 금세 통제를 벗어난다. 심지어 성능도 떨어진다. 해외 글들을 보면 요즘은 extend를 안 쓰는 추세인 것 같습니다.  
(출처링크 댓글 참조)



## 좋은 습관
Component Library를 이용하여 HTML을 구성하자. (like lego)  
<http://pflannery.github.io/oocss-skeleton.docpad/oocss/help/components.html>
semantic 스타일을 지속적으로 사용하자  
내부에 종속되지 않도록 모듈을 디자인하자  
코드를 유연하게 (width는 container가 제어하고, height은 contents가 제어하도록)  
Grid를 사랑하는 습관을 갖자.  
선택자(selector) 사용은 최소화하자  
여러개의 클래스를 적용하여 확장성을 열어두자  
CSS Lint를 사용해서 코드를 검사하자  
구조와 스킨을 독립적으로 관리(위에서 설명)  
컨테이너와 컨텐츠를 구분하자(위에서 설명)  
Reset and fonts를 사용하자 (ex. YUI) <http://yui.github.io/yui2/docs/yui_2.9.0_full/reset/index.html> 

## 나쁜 습관
의존적인 스타일을 피하자(ex .class p{…} )  
css에 html 태그를 적지 말자  
ID 사용은 피하자  
모든 이미지를 스프라이트 하지 말자  
높이를 고정 시킨 상태에서의 정렬을 피하자  
텍스트를 이미지로 사용하지 말자  
너무 이른 최적화는 피하자  
쓸모 없는 것을 두 번 반복해서 사용하지 말자  


Reference : <https://wit.nts-corp.com/2015/04/16/3538>