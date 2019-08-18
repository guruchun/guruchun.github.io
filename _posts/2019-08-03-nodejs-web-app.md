---
layout: post
title: node.js webapp 개발
category: [web]
tags: [javascript, node.js, express, bootstrap, vue.js]
---
## 개발환경
### 개발 도구
* 패키지 관리: npm
   * npm: node.js 패키지 관리자
   * bower: frontend 모듈 관리자
* 골격코드(boilerplate, scaffold) 생성
   * node.js/express
      * `npm install express-generator -g`
   * vue.js
   * 
* IDE: Visual studio code
   * intall additional extentions
      * auto close tag
      * bracket pair colorizer

### 개발 스킬
* tempalte engine
   * pug(jade): server-side에서 html 페이지를 rendering함
* 번들러, 빌드: webpack
* 라이브러리
   * lodash: javascript utility library, 기존에는 underscore를 많이 썼으나 대세는 lodash로 넘어옴

### 시작하기
* node.js/express app 생성
   * `express web --view=pug`
