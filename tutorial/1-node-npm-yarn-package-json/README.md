# 1 - Node, NPM, Yarn, and package.json

이번 절에서는 Node, NPM, Yarn 및 기본적인 `package.json` 파일을 설정합니다.

먼저 백엔드 자바 스크립트에 사용되는 Node 뿐만 아니라 현대 프론트엔드 스택을 빌드하는 데 필요한 모든 도구를 설치해야합니다.

macOS 또는 Windows 바이너리의 경우 [다운로드 페이지] (https://nodejs.org/en/download/current/)에서, Linux 배포판의 경우 [패키지 매니저 설치 페이지] (https://nodejs.org/ko/download/package-manager/)로 이동해 설치를 진행합니다.

예를 들어 **Ubuntu / Debian**의 경우 다음 명령어를 통해 Node를 설치할 수 있습니다:

```bash
curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
sudo apt-get install -y nodejs
```

Node 6.5.0 이상이라면 어떤 버전으로 설치해도 됩니다.

Node의 기본 패키지 관리자 인 `npm`은 Node와 함께 자동으로 제공되므로 별도로 설치할 필요가 없습니다.

**참고**: Node가 이미 설치되어 있는 경우 `nvm`([Node Version Manager](https://github.com/creationix/nvm))을 설치하고 최신 버전의 Node를 사용하십시오.

[Yarn] (https://yarnpkg.com/)은 NPM 보다 훨씬 빠르며, 오프라인을 지원하고, [보다 예측 가능하게] (https://yarnpkg.com/en/docs/yarn-lock) 의존성을 가져오는 또 다른 패키지 매니저 입니다. 2016년 10월에 [출시 된](https://code.facebook.com/posts/1840075619545360) 이후 매우 빠른 채택률을 보였고 JavaScript 커뮤니티가 선택한 새로운 패키지 매니저가 되었습니다. 따라서 우리는 이 자습서에서 Yarn을 사용하려고합니다. 만약 NPM을 고수하고 싶다면 이 자습서의 모든 `yarn add` 와 `yarn add --dev` 명령을 `npm install --save` 와 `npm install --save-dev`로 대체하면 됩니다.

- [사용 지침](https://yarnpkg.com/en/docs/install)에 따라 Yarn을 설치하십시오. `npm install -g yarn` 또는 `sudo npm install -g yarn`으로 설치할 수 있습니다. (네! Internet Explorer 또는 Safari를 사용하여 Chrome을 설치하는 것처럼 NPM을 사용하여 Yarn을 설치합니다!)

- 작업을 할 새로운 폴더를 만들고 `cd` 명령어를 통해 진입합니다.
- `package.json` 파일을 자동으로 생성하기 위해 `yarn init` 명령을 실행하고 질문에 답합니다. (`yarn init -y`를 통해 모든 질문을 생략할 수 있습니다)
- `index.js` 파일을 생성하고 `console.log('Hello world')`를 작성합니다.
- 폴더 내에서 `node .`를 실행합니다.(`index.js`는 현재 폴더에서 Node가 확인하는 기본 파일입니다.) 이후에 "Hello world"가 출력되어야 합니다.

우리의 프로그램을 구동시키기 위해`node .`를 실행하는 것은 약간 저수준(low-level)으로 보입니다. 대신 NPM / Yarn 스크립트를 사용하여 해당 코드의 실행을 트리거 할 수 있습니다. 이렇게 설정하면 프로그램이 더 복잡해 지더라도 언제나 `yarn start`을 통해 실행할 수 있기 때문에 멋진 추상화가 가능합니다.

- 다음과 같이 `package.json` 내 최상위 객체에 `scripts` 객체를 추가하십시오:

```json
"scripts": {
  "start": "node ."
}
```

`package.json`은 반드시 유효한 JSON 파일이어야 하기에 마지막에 쉼표를 사용할 수 없습니다. 따라서 `package.json` 파일을 직접 수정할 때는 주의해야 합니다.

- `yarn start`를 실행했을 때 `Hello world`가 출력되어야 합니다.
- `.gitignore` 파일을 만들고 다음 내용을 추가하십시오.

```gitignore
npm-debug.log
yarn-error.log
```

**참고**: 제가 제공한 `package.json` 파일을 살펴보면 모든 장에서 `tutorial-test` 스크립트를 확인할 수 있습니다. 이 스크립트를 통해 `yarn && yarn start`를 실행할 때 해당 장이 잘 작동하는지 테스트 할 수 있습니다. 물론 삭제할 수 있습니다.

다음 절: [2 - Installing and using a package](/tutorial/2-packages)

[목차로 돌아가기](https://github.com/jinro4/js-stack-from-scratch#table-of-contents)
