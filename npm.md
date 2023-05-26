# ._.) npm이란 무엇일까

### 노드 패키지 매니저 NPM

<br/>

## 🖥 NPM

NPM은 (Node Package Manger)의 약자로 명령어로 자바스크립트 라이브러리를 설치하고 관리하는 패키지 매니저입니다.

간단히 말하면 전 세계의 개발자들이 자신들이 만든 패키지와 모듈 등을 공유하고 관리하는 거대한 생태계라고 볼 수 있습니다.

개발자는 단 몇줄의 명령어로 기존의 공개된 모듈들을 설치하고 활용할 수 있습니다.

NPM(Node Package Manager)은 전 세계의 개발자들이 만든 다양한 기능(패키지, 모듈)들을 관리하는 거대한 생태계라고 할 수 있습니다.

우리는 이 npm에 공개되어 있는 코드들을 가져오기만 하면, 복잡하고 고도화된 기능을 손쉽게 사용할 수 있습니다.

<br/>

### 🖐🏻 잠깐! 여기서 패키지란 ?

- 라이브러리 - 코드의 작성을 위해 사용되는 코드의 묶음

- 패키지 - 코드의 배포를 위해 사용되는 코드의 묶음

- 컴파일한 소프트웨어의 바이너리, 환경설정(configuration) 관련정보, 의존(dependency)관련정보

- 패키지는 라이브러리를 포함할 수도 있으며, 일반적으로 라이브러리와 실행파일을 포함한다.

<br/>

### ⌨️ 의존성 관리

프로젝트에서는 아주 많은 패키지를 사용하게 되고 이런 패키지들의 버전이 빈번하게 업데이트 되므로 프로젝트가 의존하고 있는 패키지들이 관리될 필요가 있습니다.
npm에서는 `package.json` 파일로 프로젝트의 정보와 패키지들의 의존성을 관리합니다.

<br/>

### ⌨️ package.json이란?

프로젝트를 진행하다보면 수많은 패키지들을 추가하게 됩니다.

이러한 패키지들은 저마다의 고유한 버전이 있는데, 이것들을 기록하고 관리해주는 파일이 바로 `package.json` 입니다.

때문에 기본적으로 프로젝트 내에서 npm을 사용하려면 프로젝트 내에 package.json 파일이 존재해야 합니다.

package.json 파일을 생성하기 위해선 다음 명령어를 터미널에 입력합니다.

```sh
$ npm init
```

이것은 npm으로 패키지를 관리하겠다라는 의미이기도 합니다.

package.json 파일 내부로 가서 구성을 보시면 다음과 같습니다.

<br/>

```json
{
  "name": "test",
  "description": "javascript's test programming.",
  "keywords": ["util", "f", "server", "client", "browser"],
  "author": "Goorm",
  "contributors": [],
  "dependencies": [],
  "repository": {
    "type": "git",
    "url": "git://gitbub.com/documentcloud/test.git"
  },
  "main": "test.js",
  "version": "1.1.6"
}
```

| 옵션        | 설명                                                                                                      |
| ----------- | --------------------------------------------------------------------------------------------------------- |
| name        | 프로젝트 이름                                                                                             |
| version     | 프로젝트의 버전                                                                                           |
| description | 프로젝트에 대한 간단한 설명                                                                               |
| main        | 프로그램의 시작점이 되는 모듈의 ID (우리도 npm 생태계에 올릴 수 있게 하는 옵션)                           |
| scripts     | 현재 프로젝트 내부에서 사용할 수 있는 스크립트 명령들 ("명령이름": "명령~" -> 터미널 $ npm run 명령이름 ) |
| author      | 소유주                                                                                                    |
| license     | 다른 사용자들이 이 패키지를 사용할 때 필요한 권한                                                         |

<br/><br/>

## 🖥 npm 사용하기

아래 명령어를 입력하면 원하는 패키지를 설치할 수 있습니다.

```sh
npm install '패키지명'
```

* `npm install -D '패키지명'` : 이 패키지를 사용해서 개발하되, 서버가 배포된 이후에는 사용되지 않을때 -D를 사용합니다.

* `npm install -g'패키지명'` : 패키지를 모두 공통적으로 설치하겠다는 의미입니다.


<br/><br/><br/>

---

## 참고

- [About NPM](https://docs.npmjs.com/about-npm)
- [What is NPM](https://www.w3schools.com/whatis/whatis_npm.asp)
- [npm이란 무엇인가?](https://velog.io/@yoojinpark/npm)
