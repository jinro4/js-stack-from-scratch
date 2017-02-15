# JavaScript Stack from Scratch

[![Build Status](https://travis-ci.org/verekia/js-stack-from-scratch.svg?branch=master)](https://travis-ci.org/verekia/js-stack-from-scratch) [![Join the chat at https://gitter.im/js-stack-from-scratch/Lobby](https://badges.gitter.im/js-stack-from-scratch/Lobby.svg)](https://gitter.im/js-stack-from-scratch/Lobby)

[![Yarn](/img/yarn.png)](https://yarnpkg.com/)
[![React](/img/react.png)](https://facebook.github.io/react/)
[![Gulp](/img/gulp.png)](http://gulpjs.com/)
[![Redux](/img/redux.png)](http://redux.js.org/)
[![ESLint](/img/eslint.png)](http://eslint.org/)
[![Webpack](/img/webpack.png)](https://webpack.github.io/)
[![Mocha](/img/mocha.png)](https://mochajs.org/)
[![Chai](/img/chai.png)](http://chaijs.com/)
[![Flow](/img/flow.png)](https://flowtype.org/)

모던 자바스크립트 스택 튜토리얼에 온 것을 환영합니다: **JavaScript Stack from Scratch**.

> ⚠️️ 이 자습서의 주요 업데이트가 2월 안에 제공될 예정입니다, 조금만 기다려주세요! [Read more](https://github.com/verekia/js-stack-from-scratch/issues/133).

본 내용은 JavaScript 스택을 조립하기 위한 최소한의 지침입니다. 일반적인 프로그래밍 지식과 JavaScript 기초가 필요합니다. 또한 **연결된 도구들을 함께** 사용하는 것에 초점을 맞추고 각 도구에 대해 **가능한 가장 간단한 예제를 제공합니다.** 이 자습서는 *나만의 상용구(boilerplate) 만들기* 로 볼 수도 있습니다.

물론 몇 가지 JS 상호 작용이 포함 된 간단한 웹 페이지를 작성하는 경우 전체 스택을 사용할 필요는 없습니다. (Browserify / Webpack + Babel + jQuery의 조합으로 CLI 컴파일을 사용하여 다른 파일에 ES6 코드를 작성할 수 있습니다.) 하지만 확장성 있는 웹 애플리케이션을 만들거나 설정하려는데 도움이 필요하다면 이 자습서는 여러분에게 도움이 될 것 입니다.

이 튜토리얼의 목표는 다양한 도구를 조합하는 것이므로 각 도구들이 어떻게 작동하는지에 대해서는 자세히 설명하지 않습니다. 만약 더 깊은 지식을 얻기 원할 경우 해당 도구의 공식 문서를 참조하거나 다른 자습서를 찾아보세요.

이 튜토리얼에서 설명할 스택의 큰 덩어리는 React가 차지합니다. 만약 여러분이 React를 배우고 싶다면, [create-react-app](https://github.com/facebookincubator/create-react-app)은 미리 만들어놓은 사전 설정을 통해 매우 빠르게 React 환경을 기동 할 수 있게 해줍니다.

예를 들어 누군가 React를 사용하는 팀에 합류해서 빠르게 React를 학습시키고 가지고 놀게 하고 싶다면 `create-react-app`을 사용하는 접근법도 괜찮습니다.

하지만 이 자습서에서는 사전 설정을 사용하지 않을 것입니다. 왜냐하면 저는 여러분들이 내부적으로 일어나고 있는 모든 과정을 이해하길 원하기 때문입니다.

코드 예제는 각 장에서 사용할 수 있으며`yarn && yarn start` 또는`npm install && npm start`로 모두 실행할 수 있습니다. 각 장의 **단계별 지침**을 따라 처음부터 모든 것을 직접 작성하는 것을 추천 드립니다.

**모든 장에는 이전 장의 코드**가 포함되어 있습니다. 따라서 모든 내용이 포함 된 상용구(boilerplate) 프로젝트를 찾고 있다면 마지막 장을 복제하면 됩니다.

참고: 각 장의 순서가 무조건 옳지는 않습니다. 예를 들어, React를 도입하기 전에 테스트 / 타입 검증을 진행 할 수도 있습니다. 자습을 진행하는 중에 다른 장, 혹은 이전 장을 수정하는 것은 쉽지 않습니다. 이후의 진행될 모든 장에 변경 사항을 적용해야하기 때문입니다. 여유가 생기면 더 좋은 방법을 고민해보겠습니다.

이 자습서의 코드는 Linux, macOS, Windows에서 동작합니다.

## 목차

[1 - Node, NPM, Yarn, and package.json](/tutorial/1-node-npm-yarn-package-json)

[2 - Installing and using a package](/tutorial/2-packages)

[3 - Setting up ES6 with Babel and Gulp](/tutorial/3-es6-babel-gulp)

[4 - Using the ES6 syntax with a class](/tutorial/4-es6-syntax-class)

[5 - The ES6 modules syntax](/tutorial/5-es6-modules-syntax)

[6 - ESLint](/tutorial/6-eslint)

[7 - Client app with Webpack](/tutorial/7-client-webpack)

[8 - React](/tutorial/8-react)

[9 - Redux](/tutorial/9-redux)

[10 - Immutable JS and Redux Improvements](/tutorial/10-immutable-redux-improvements)

[11 - Testing with Mocha, Chai, and Sinon](/tutorial/11-testing-mocha-chai-sinon)

[12 - Type Checking with Flow](/tutorial/12-flow)

## 이후에 진행할 것들

운영 / 개발 환경 설정, Express, React Router, 서버-사이드 렌더링, 스타일링, Enzyme, Git Hooks.

## Translations

- [中文](https://github.com/pd4d10/js-stack-from-scratch) by [@pd4d10](http://github.com/pd4d10)
- [Italiano](https://github.com/fbertone/js-stack-from-scratch) by [Fabrizio Bertone](https://github.com/fbertone)
- [日本語](https://github.com/takahashim/js-stack-from-scratch) by [@takahashim](https://github.com/takahashim)
- [Русский](https://github.com/UsulPro/js-stack-from-scratch) by [React Theming](https://github.com/sm-react/react-theming)
- [ไทย](https://github.com/MicroBenz/js-stack-from-scratch) by [MicroBenz](https://github.com/MicroBenz)
- [한국어](https://github.com/jinro4/js-stack-from-scratch) by [Tamm](https://github.com/jinro4)

만약 새로운 번역을 추가하고 싶다면 [translation recommendations](/how-to-translate.md)를 읽고 시작하세요!

## Credits

Created by [@verekia](https://twitter.com/verekia) – [verekia.com](http://verekia.com/).

License: MIT
