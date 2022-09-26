# 
# ._.) 스코프와 호이스팅을 알아보자.
### 스코프와 호이스팅
<br/>

* 스코프(scope)란 변수의 유효 범위를 말한다.

* 예를 들어, "변수 x의 스코프는 y이다"라는 말은 "변수 x는 y 영역에서 참조할 수 있다"는 말과 같다.

* 자바스크립트는 렉시컬 스코프(lexical scope)를 따른다.

* 렉시컬 스코프는 스코프를 결정하는 방식 중 하나인데, 좀 더 정확히 말하면 상위 스코프를 결정하는 방식이다.

이 개념을 이해하기에 앞서 '전역/지역 스코프'와 '함수/블록 레벨 스코프'를 알아보자.
<br/><br/>

## 🖥 전역/지역 스코프

```js
// >> 🌏 전역 시작
var x = 'global x'
var y = 'global y'

function foo() {
  // >> 📍 지역 시작
  var y = 'local y'
  console.log(x)
  // 📍 지역 끝 <<
}

foo() // ①
console.log(y) // ②
// 🌏 전역 끝 <<
```

* 전역이란, 코드의 가장 바깥 영역을 말하고, 이 영역에 선언된 변수는 전역 스코프를 갖는 전역 변수가 된다.

  * 전역 변수는 어디서든지 참조할 수 있는 변수이다.

* 지역이란, 함수 몸체 내부를 말하고, 이 영역에 선언된 변수는 지역 스코프를 갖는 지역 변수가 된다.

  * 지역 변수는 자신의 지역 스코프와 하위 지역 스코프까지 유효하다.
<br/>

### ⌨️ 스코프에 의한 식별자 결정
위 코드에서 의도한 `foo()` 함수의 기능은 다음과 같다.

* 변수 x 값 출력

* 변수 y 값 재할당

①의 결과는 `'global x'` 이다.
②의 결과는 변수 y 값이 재할당이 되었으니 'local y' 라고 생각할 수 있지만 `'global y'` 이다.

> 사실 두 변수(전역 변수 y, 지역 변수 y)는 동명이인처럼 이름만 같은 별개의 변수이다. 변수는 자신이 선언된 위치에 의해 스코프가 결정된다.

👉 즉, 함수 내에 선언된 변수는 해당 함수 밖에서 참조가 불가능하다.

이와 같이 자바스크립트가 두 개 이상의 변수 중 참조할 하나의 변수를 결정하는 것을 식별자 결정이라고 한다.
<br/><br/>

## 🖥 함수/블록 레벨 스코프
```js
// 코드 블록
{ ... }

// 함수 레벨 스코프
function foo() {
  /* 지역 스코프 */
}

// 블록 레벨 스코프 (if, for, while 등 모든 코드 블록)
if (...) {
  /* 지역 스코프 */
}

for (...) {
  /* 지역 스코프 */
}

while (...) {
  /* 지역 스코프 */
}
```

함수 레벨 스코프란 함수의 코드 블록 내에서만 지역 스코프를 생성하는 것을 말하고,

블록 레벨 스코프란 함수뿐만 아니라 모든 코드 블록 내에서 지역 스코프를 생성하는 것을 말한다.

> * 함수 레벨 스코프 : __var__

> * 블록 레벨 스코프 : __let__, __const__

`var` 변수는 함수 내에 선언되지 않을 경우 항상 전역 변수가 된다.

❗️이는 변수가 다른 곳에서 의도치 않게 참조되거나 값이 변경될 수 있다는 의미여서 각별히 주의해야 한다.
<br/><br/>

## 🖥 상위/하위 스코프
```
// global
var x = 'global x'

// outer
function outer() {
  
  // inner
  function inner() {
    var x = "inner x"
  }
  
  inner()
  console.log(x)
}

outer() // ?
```



<br/><br/><br/>

***
## 참고
* [[JavaScript] 렉시컬 스코프(lexical scope)](https://velog.io/@bico/JavaScript-%EB%A0%89%EC%8B%9C%EC%BB%AC-%EC%8A%A4%EC%BD%94%ED%94%84lexical-scope)
* [스코프와 호이스팅](https://edu.goorm.io/learn/lecture/557/%ED%95%9C-%EB%88%88%EC%97%90-%EB%81%9D%EB%82%B4%EB%8A%94-node-js/lesson/226443/%EC%8A%A4%EC%BD%94%ED%94%84%EC%99%80-%ED%98%B8%EC%9D%B4%EC%8A%A4%ED%8C%85)
* [JavaScript - 스코프(Scope)](https://youngjinmo.github.io/2021/08/js-scope/)
* [[JavaScript] 스코프(Scope)와 변수 선언 (var, let, const 키워드 차이점)](https://hanamon.kr/javascript-%EC%8A%A4%EC%BD%94%ED%94%84%EC%99%80-%EB%B3%80%EC%88%98%EC%84%A0%EC%96%B8%ED%82%A4%EC%9B%8C%EB%93%9C-%EC%B0%A8%EC%9D%B4%EC%A0%90/)
* [자바스크립트 스코프(Scope)](https://velog.io/@solseye/JS-%EC%9E%98-%EB%B4%90-%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EC%8A%A4%EC%BD%94%ED%94%84Scope-%EC%8B%B8%EC%9B%80%EC%9D%B4%EB%8B%A4)
