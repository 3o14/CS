# ._.) 모듈을 배워보자
### 뭐라적지
<br/>

## 🖥 모듈이란?
프로그래밍에서 모듈이란 프로그램을 구성하는 구성요소의 일부

개발하는 애플리케이션의 크기가 커지면 확장성과 유지보수 측면에서 파일을 여러 개로 분리하는 시점이 온다.

이때 분리된 파일 각각을 '모듈'이라고 부르고, 보통 클래스 하나 혹은 특정한 목적을 가진 복수의 함수로 구성된 라이브러리 하나로 구성된다.

<br/>


### 📍 모듈화의 장점
* 프로그램의 효율적인 관리 및 성능 향상

* 전체적인 소프트웨어 이해의 용이성 증대 및 복잡성 감소

* 소프트웨어 디버깅, 테스트, 통합, 수정 시 용이성 제공

* 기능의 분리가 가능하고 인터페이스가 단순

* 오류의 파급효과를 최소화

* 모듈의 재사용 가능으로 개발과 유지보수가 용이
<br/><br/>

## 🖥 모듈 시스템

* __CommonJS:__ Node.js 서버를 위해 만들어진 모듈 시스템

* __AMD:__ 가장 오래된 모듈 시스템 중 하나로 require.js라는 라이브러리를 통해 처음 개발됨

* __UMD:__ AMD와 CommonJS와 같은 다양한 모듈 시스템을 함께 사용하기 위해 등장

### ⌨️ CommonJS

* 다른 모듈을 사용할 때는 `require` 를, 모듈을 해당 스코프 밖으로 보낼 때에는 `module.exports` 를 사용하는 방식

* Node.js에선 현재 이 방식을 사용하고 있다.

hello world를 출력하는 함수를 가진 파일을 `usedBy.js` 라고 하고 그 함수를 가져와서 사용하는 파일을 `byUsing.js` 라고 하면 다음과 같이 사용할 수 있다.

#### __`usedBy.js`__

```js
const printHelloWorld = () => {
  console.log('Hello Wolrd');
};

module.exports = {
  printHelloWorld
};
```

#### __`byUsing.js`__

```js
const func = require('./a.js'); // 같은 디렉토리에 있다고 가정
func.printHelloWorld();
```

* 여기서 `module.exports` 의 `module` 은 현재 모듈에 대한 정보를 갖고 있는 객체이다.
* 이는 예약어이며 그 안에 `id` , `path` , `parent` 등의 속성이 있고 `exports` 객체를 가지고 있다.

<details>
<summary> 접기/펼치기 </summary>
<div markdown="1">

  <br/>
  
`module.exports` 외에도 `exports` 를 사용하기도 하는데 이 관계에 대해서 명확히 이해하고 있어야 한다.

정리하자면 아래와 같다.

* module.exports 는 빈 객체를 참조한다.

* exports 는 module.exports 를 참조한다.

* require 는 항상 module.exports 를 리턴받는다.

<br/>
  
즉, 함수를 모듈 밖으로 내보내고자 할 때는 위에 예시에서 2가지 모두 사용할 수 있다.

```js
exports.printHelloWorld = printHelloWorld;
module.exports = { printHelloWorld };
```
  
<br/>
  
그렇다면 왜 2가지를 설정해놓았을까?
  
  그 이유는 `exports` 는 항상 `module.exports` 를 참조하기 때문에 `exports` 를 사용하면 직접 `module.exports` 를 수정하지 않고 객체의 멤버를 만들거나 수정하는 방식으로 사용한다. 따라서, `exports` 에 어떤 값을 할당하거나 새로운 객체를 할당했다고 하더라도 결국 `require` 는 `module.exports` 를 리턴받기 때문에 잠재적인 버그를 피할 수가 있다.
</div>
</details>

<br/>

### ⌨️ AMD(Asynchronous Module Definition)

* Asynchronous: 동시에 존재[발생]하지 않는, 실시간이 아닌

`CommonJS`가 서버쪽에서 장점이 많은 반면에, `AMD`는 브라우저 쪽에서 더 큰 효과를 발휘한다.

브라우저에서는 모든 모듈이 다 로딩될 때까지 기다릴 수 없기 때문에 비동기 모듈 로딩방식으로 구현을 해놓았다. 

이 방식에서 사용하는 함수는 `define()` 과 `require()` 이며 AMD 스펙을 가장 잘 구현한 모듈로더는 `RequireJS` 이다. 

한번 간단한 예시로 사용해보자.

#### __`index.html`__

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Document</title>
</head>
<body>
  <script data-main="index.js" src="require.js"></script>
</body>
</html>
```
`require.js` 파일을 받아서 `<script>` 태그에 넣어주고 `data-main` 속성으로 `require.js` 가 로드된 후에 실행할 자바스크립트 파일 경로를 넣어준다.

즉, `require.js` 가 로드되자마자 `index.js` 가 실행되는 구조이다.

<br/>

#### __`index.js`__

```js
require.config({
  baseUrl: '/',
  paths: {
    a: 'a',
    b: 'b',
  }
});

require(['a'], (a) => {
  a.printA();
});
```

`require.config` 는 설정부분으로 기본 경로와 각 모듈에 해당하는 경로를 설정해준다.

그 다음 `require` 를 통해서 첫번째 인자에 해당하는 모듈이 로드되었을 경우에 그걸 `a` 로 받아서 `printA()` 함수를 호출하는 콜백함수를 실행한다. 의존성 모듈을 지정해주는 것이다.

<br/>

#### __`a.js`__

```js
define(() => {
  return {
    printA: () => console.log('a')
  }
});
```
모듈 `a`는 위와 같이 만들어져 있고 `define()` 을 통해서 정의된다.

여기서도 `require()` 에서 의존성 모듈을 설정해준 것처럼 콜백함수가 실행되기 전에 로드되어야 할 모듈들을 지정해줄 수 있다.

<br/>

### ⌨️ UMD(Universal Module Definition)

위에서 살펴본 바로, 모듈 구현방식이 CommonJS 와 AMD로 나뉘기 때문에 그걸 통합하기 위한 하나의 패턴이라고 할 수 있다.

[공식 umd 소스코드](https://github.com/umdjs/umd/blob/master/templates/returnExports.js) 를 살펴보면 아래와 같다.

```js
(function (root, factory) {
    if (typeof define === 'function' && define.amd) {
        // AMD. Register as an anonymous module.
        define([], factory);
    } else if (typeof module === 'object' && module.exports) {
        // Node. Does not work with strict CommonJS, but
        // only CommonJS-like environments that support module.exports,
        // like Node.
        module.exports = factory();
    } else {
        // Browser globals (root is window)
        root.returnExports = factory();
  }
}(typeof self !== 'undefined' ? self : this, function () {

    // Just return a value to define the module export.
    // This example returns an object, but the module
    // can return a function as the exported value.
    return {};
}));
```









