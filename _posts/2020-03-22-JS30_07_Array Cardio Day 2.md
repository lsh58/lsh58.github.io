---
layout: post
title: "JS30_07_Array Cardio Day 2"
description:
headline:
modified: 2020-03-22
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

# JS30_07_Array Cardio Day 2

*초기 코드(Type Aheady index-START.html)
<div class="code">
<iframe width="100%" height="300" src="//jsfiddle.net/lsh58/tbsouLvc/embedded/html,result/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

### 목표
배열에 대해 공부합니다.2탄.

```
    // Some and Every Checks
    // Array.prototype.some() // is at least one person 19 or older?
    // Array.prototype.every() // is everyone 19 or older?


    // Array.prototype.find()
    // Find is like filter, but instead returns just the one you are looking for
    // find the comment with the ID of 823423


    // Array.prototype.findIndex()
    // Find the comment with this ID
```

### 공부한 내용  

<span class="orange">some()</span>  
some() function은 callback function을 인자로 받고 이 callback function은 boolean타입을 리턴하도록 정의해야 한다. 배열의 매 요소마다 callback function의 인자로 받아 함수를 실행하며, 하나의 true값만 리턴한다면 some()은 true를 리턴한다.

<span class="orange">every()</span>  
every()는 함수명에서 오는 느낌대로 배열의 **모든** 요소들이 callback function에서 true를 리턴하는지를 확인해준다. 따라서 1번 문제와 같은 callback함수를 사용하면 된다.

<span class="orange">find()</span>  
find() function 역시 callback function을 인자로 받으며, 해당 함수값이 true를 리턴하는 첫 번째 인자를 반환한다. 

<span class="orange">findIndex()</span>  
findIndex() function은 find() function과 같지만 해당 객체가 아닌 객체의 index를 반환하는 함수이다.

*전체 자바스크립트 코드
<div class="code">
<iframe width="100%" height="300" src="//jsfiddle.net/lsh58/tbsouLvc/3/embedded/js/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>


Reference : <https://medium.com/@benjaminwoojang/array-cardio-day2-fcd2c3c32857>