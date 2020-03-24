---
layout: post
title: "JS30_09_Dev Tools Domination"
description:
headline:
modified: 2020-03-23
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

# JS30_09_Dev Tools Domination

*초기 코드(Type Aheady index-START.html)
<div class="code">
<iframe width="100%" height="400" src="//jsfiddle.net/lsh58/xn345ovh/embedded/html/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>

### 목표
브라우저의 콘솔창에 관한 함수들의 사용법을 공부해봅니다.

### 공부한 내용  
// Regular console.log('hello'); // 기본적인 콘솔 로그입니다. 

// Interpolated console.log('Hello I am a %s string!', '💩'); // 형식 지정자를 이용한 콘솔 로그입니다. 

// Styled console.log('%c I am some great text', 'font-size:50px; background:red; text-shadow: 10px 10px 0 blue'); // %c를 붙이면 , 뒤에 오는 텍스트는 style 옵션입니다. 

// warning! console.warn('OH NOOO'); // 노란색 경고 표시로 출력됩니다. 

// Error :| console.error('Shit!'); // 빨간색 에러 표시로 출력됩니다. 

// Info console.info('Crocodiles eat 3-4 people per year'); // 콘솔창에서 텍스트앞에 정보 아이콘 출력된다고합니다. 

// Testing const p = document.querySelector('p'); console.assert(p.classList.contains('ouch'), 'That is wrong!'); // 클래스리스트에 ouch를 포함하고 있지 않으면 That is wrong! 이라는 assertion을 일으키고 출력한다. 

// clearing console.clear(); // 콘솔창을 깨끗하게 만든다.  

// Viewing DOM Elements  
console.log(p);  
console.dir(p);  
console.clear();  

// Grouping together dogs.forEach((dog) => { console.groupCollapsed(`${dog.name}`); // groupCollapsed는 그룹핑할 타이틀이라고 생각하면 된다.  
console.log(`This is ${dog.name}`); // 그룹핑할 첫 번째 로그.  
console.log(`${dog.name} is ${dog.age} years old`); // 그룹핑할 두 번째 로그.  
console.groupEnd(`${dog.name}`); // 여기까지 그룹핑한다. });  
 
// counting console.count('Wes'); // 입력된 텍스트로 몇번 카운트되었는지 출력.   
console.count('Wes');  
console.count('Steve');  
console.count('Steve');  
console.count('Wes');  
console.count('Steve');  
console.count('Wes');  
console.count('Steve');  
console.count('Steve');  
console.count('Steve');  
console.count('Steve');  
console.count('Steve');  

// timing console.time('fetching data'); // console.timeEnd가 호출되기 전까지 시간 측정.  
fetch('https://api.github.com/users/wesbos')   
.then(data => data.json())   
.then(data => { console.timeEnd('fetching data'); // console.time이 호출된때부터 시간이 얼마나 흘렀는지 출력.   
console.log(data); }); console.table(dogs);  


*전체 자바스크립트 코드
<div class="code">
<iframe width="100%" height="500" src="//jsfiddle.net/lsh58/xn345ovh/2/embedded/js/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>
</div>


Reference : <https://orashelter.tistory.com/73>