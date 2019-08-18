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


## 개발환경
### 개발 도구
* 패키지 관리
   * npm: node.js 패키지 관리자
   * bower: frontend 모듈 관리자
* IDE: Visual studio code
   * Intall additional extentions
      * auto close tag
      * bracket pair colorizer
* Framework
   * Backend-side: Node.js/Express
   * Database: Mongodb
   * Frontend-side: Vue.js
   * Native app: nativescript
* 골격코드(boilerplate, scaffold) 생성
   * For Node.js/express
      * `npm install express-generator -g`
   * For Vue.js
      * `vue-cli` with 'vue-admin-template'
   * For nativescript
      * https://nativescript-vue.org/ko/
      * https://github.com/Gonzalo2310/awesome-nativescript-vue
      * `tns create sample-app --template nativescript-vue-template`
      * 미완성, 'nativescript-vue-webpack-template'
   * For Desktop
      * `electron-vue` with 'electron-vue-admin'
   * For Admin. Tempalte: 미정, 아래는 후보들...
      * https://github.com/flatlogic/sing-app-vue-dashboard
      * https://github.com/PanJiaChen/vue-element-admin
      * https://colorlib.com/polygon/gentelella/index.html

### 개발 스킬
* tempalte engine
   * pug(jade): server-side에서 html 페이지를 rendering함
* CSS 전처리기
   * 
* 번들러, 빌드: webpack
* 라이브러리
   * lodash: javascript utility library, 기존에는 underscore를 많이 썼으나 대세는 lodash로 넘어옴

### 시작하기
* node.js/express app 생성
   * project='web', view template engine='pug'
   * `express web --view=pug`
* app에서 필요한 모듈 다운로드(설치하기)
   * package.json에 프로젝트에서 참조하는 모듈이 정의되어 있음
   * npm을 통해 package.json에 있는 모듈을 한번에 설치함
   * `npm install`
