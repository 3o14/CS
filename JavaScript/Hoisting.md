# ._.) 호이스팅(Hoisting)이 무엇일까요?
### 함수 안에 있는 선언들을 모두 끌어올려서 해당 함수 유효 범위의 최상단에 선언하는 것
<br/>

## 🖥 호이스팅이란
* 자바스크립트 함수는 실행되기 전에 함수 안에 필요한 변수값들을 모두 모아서 유효 범위의 최상단에 선언한다.
  
  * 자바스크립트 Parser가 함수 실행 전 해당 함수를 한 번 훑는다.
  
  * 함수 안에 존재하는 변수/함수선언에 대한 정보를 기억하고 있다가 실행시킨다.
  
  * 유효 범위: 함수 블록 `{}` 안에서 유효

* 즉, 함수 내에서 아래쪽에 존재하는 내용 중 필요한 값들을 끌어올리는 것이다.
  * 실제로 코드가 끌어올려지는 건 아니며, 자바스크립트 Parser 내부적으로 끌어올려서 처리하는 것이다.

  * 실제 메모리에서는 변화가 없다.
<br/><br/>

## 🖥 호이스팅의 대상
### var
* `var`로 선언한 변수는 호이스팅시 `undefined`로 변수를 초기화한다.

* 선언 이전에 사용하려고 했을 때 -> undefined가 출력

### let, const
* `let`과 `const`로 선언한 변수는 호이스팅시 변수를 초기화하지 않는다.

* 선언 이전에 사용하려고 했을 때 -> 에러가 뜸
<br/><br/>

## 🖥 함수와 변수 호이스팅
호이스팅은 함수와 변수로 나눌수 있는데, 이 때 함수는 함수선언으로 작성된 경우를 말한다.

```js
함수선언

function calcRectArea(width, height) {
  return width * height;
}
console.log(calcRectArea(5, 6));
// expected output: 30


함수표현식

const getRectArea = function(width, height) {
  return width * height;
};
console.log(getRectArea(3, 4));
// expected output: 12
```

함수표현식의 경우 결국 변수에 함수를 할당하는 형태여서 변수 호이스팅에 해당한다.

### ⌨️ 함수 호이스팅
함수 호이스팅이 가장 먼저 이루어진다.

함수의 선언문은 식별자가 변수 객체에 수집될 때 부가적으로 함수의 참조에 대한 초기화까지 자동으로 이루어지기 때문에 __상단에서 참조, 호출이 가능__ 하다.
<br/>

### ⌨️ 변수 호이스팅

```js
{ // declaration (hoisted)
  // Temporal deadzone
  let foo; // declaration and initialization to undefined
  foo = 1; // assignment
}
```

호이스팅을 통해 선언이 스코프 최상단에서 일어난다.

그리고 실제 선언문은 let foo;에서 일어나며, 이 때 `undefined`로 초기화된다.

그리고 그 아래에 foo = 1;에서 할당이 되며 변수에 값이 저장된다.


___! const는 값을 할당하지 않고 선언만 하는것이 불가능하다(const foo;이런식으로)___
<br/><br/>

## 📍 규칙성
앞서 살펴본 함수, 변수의 호이스팅 과정을 정리하여 규칙을 나타내본다면 다음과 같다.

* 선언된 함수는 선언문 상단에서 참조, 호출이 가능하다.

* `var`로 선언된 변수는 선언문 상단에서 참조, 할당이 가능하다.

* `let`, `const`로 선언된 변수는 상단에서 참조, 할당이 불가능하다.
<br/><br/><br/>

***
## 참고
* [[JacaScript] 호이스팅(Hoisting)이란](https://gmlwjd9405.github.io/2019/04/22/javascript-hoisting.html)
* [Javascript 호이스팅](https://velog.io/@leejihun96/Javascript-%ED%98%B8%EC%9D%B4%EC%8A%A4%ED%8C%85)
* [호이스팅(Hoisting) 이란?](https://velog.io/@hoo00nn/%ED%98%B8%EC%9D%B4%EC%8A%A4%ED%8C%85Hoisting-%EC%9D%B4%EB%9E%80)
* [Mdn web docs - 호이스팅 ](https://developer.mozilla.org/ko/docs/Glossary/Hoisting)
