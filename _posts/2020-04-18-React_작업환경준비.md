---
layout: post
title: "React_작업환경준비"
description:
headline:
modified: 2020-04-18
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

# React_작업환경준비

# 설치해야할 항목

Node.js: Webpack 과 Babel 같은 도구들이 자바스크립트 런타임인 Node.js 를 기반으로 만들어져있습니다. 그렇기에 해당 도구들을 사용하기 위해서 Node.js 를 설치합니다.  
[설치링크](https://nodejs.org/en/)  

Yarn: Yarn 은 조금 개선된 버전의 npm 이라고 생각하시면 됩니다. npm 은 Node.js 를 설치하게 될 때 같이 딸려오는 패키지 매니저 도구입니다. 프로젝트에서 사용되는 라이브러리를 설치하고 해당 라이브러리들의 버전 관리를 하게 될 때 사용하죠. 우리가 Yarn 을 사용하는 이유는, 더 나은 속도, 더 나은 캐싱 시스템을 사용하기 위함입니다.  
[설치링크](https://classic.yarnpkg.com/en/docs/install#windows-stable)

코드 에디터: 그리고, 코드 에디터를 준비하세요. 여러분이 좋아하는 에디터가 있다면, 따로 새로 설치하지 않고 기존에 사용하시던걸 사용하셔도 됩니다. 저는 주로 VSCode 를 사용합니다. 이 외에도, Atom, WebStorm, Sublime 같은 훌륭한 선택지가 있습니다.  

Git bash: 윈도우의 경우, Git for Windows 를 설치해서 앞으로 터미널에 무엇을 입력하라는 내용이 있으면 함께 설치되는 Git Bash 를 사용하세요. 윈도우가 아니라면 설치하지 않으셔도 상관없습니다. 설치는 기본 옵션으로 진행하시면 됩니다.

# 새 프로젝트 만들어보기

새로운 리액트 프로젝트를 만들어봅시다. 터미널을 열은 뒤, 다음 명령어를 실행해보세요. (윈도우 사용자는 Git Bash 를 사용하세요)
먼저, 터미널에서 폴더를 하나 생성해줍니다.
```
mkdir 폴더명
```
해당 폴더로 이동해줍니다.
```
cd 폴더명
```
해당 폴더에서 react app을 생성해줍니다.
```
$ npx create-react-app begin-react
```
그러면 begin-react 라는 디렉터리가 생기고 그 안에 리액트 프로젝트가 생성됩니다. 생성이 끝나면 cd 명령어를 사용하여 해당 디렉터리에 들어간 다음 yarn start 명령어를 입력해보세요 (yarn 이 없다면 npm start).
```
$ cd begin-react
$ yarn start
```
이 명령어를 실행하고 나면 다음과 같이 브라우저에 http://localhost:3000/ 이 열리고, 돌아가는 리액트 아이콘이 보일 것입니다. 자동으로 페이지가 열리지 않는다면 브라우저에 주소를 직접 입력하여 들어가세요.


