# 2 - Installing and using a package

이번 절에서는 패키지를 설치하고 사용하는 방법에 대해 알아보겠습니다. "패키지"는 쉽게 말해 다른 사람이 작성한 코드 조각으로 여러분의 코드에서 사용할 수 있습니다. 이는 여러가지가 종류가 있을 수 있는데 이번에는 색상을 조종할 수 있는 패키지를 사용해 보겠습니다.

-`yarn add color`을 실행하여 커뮤니티에서 만든 `color` 패키지를 설치하십시오.

`package.json`을 확인해보면 Yarn이 `dependencies` 부분에 `color` 패키지를 자동으로 추가한걸 확인할 수 있습니다.

`node_modules` 폴더는 패키지를 저장하기 위해 생성됩니다.

여러분의 `.gitignore` 파일에 `node_modules/`를 추가하십시오. (만약 `git init`을 명령을 사용하지 않았다면 이를 실행해 새로운 저장소를 만드십시오)

또한 Yarn을 통해`yarn.lock` 파일이 생성되었음을 확인할 수 있습니다. 이 파일을 저장소에 커밋해야 팀의 모든 사람이 동일한 버전의 패키지를 사용할 수 있습니다. Yarn 대신 NPM을 사용하는 경우 이 파일과 동일한 역할을 하는 *shrinkwrap*이 사용됩니다.

- `index.js`에 `const Color = require('color');`를 추가하십시오
- `color` 패키지는 이렇게 사용할 수 있습니다: `const redHexa = Color({r: 255, g: 0, b: 0}).hex();`
- `console.log(redHexa)`를 추가하십시오.
- `yarn start`를 실행하면 `#FF0000`이 출력되어야 합니다.

축하합니다! 여러분은 패키지를 설치하고 사용해봤습니다!

`color` 패키지는 간단한 패키지 사용법을 가르쳐주기 위해 사용했기에 이번 절에서만 사용됩니다. 이제 더이상 필요하지 않기 때문에 다음과 같이 삭제할 수 있습니다:

- Run `yarn remove color`
- `yarn remove color`를 실행하십시오.

**참고**: 패키지 의존성은(package dependencies) 2가지 종류가 있습니다. `"dependencies"`와 `"devDependencies"`가 존재하는데, `"dependencies"`는 프로덕션 환경에서 사용합니다. `"devDependencies"`는 프로덕션 환경이 아닌 개발 환경에서 필요한 패키지들을 포함하면 됩니다.(일반적으로 빌드와 관계된 패키지 들이나 linter 등) `"devDependencies"`를 설정하기 위해서는 `yarn add --dev [package]`를 사용하면 됩니다.

다음 절: [3 - Setting up ES6 with Babel and Gulp](/tutorial/3-es6-babel-gulp)

[이전 절로 이동하기](/tutorial/1-node-npm-yarn-package-json) 또는 [목차로 돌아가기](https://github.com/jinro4/js-stack-from-scratch#table-of-contents).
