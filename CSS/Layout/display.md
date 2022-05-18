# ._.) display를 알아보자
### display는 요소(element) 의 종류를 선택하는 속성이다.
<br/>

## 🖥 display 속성이란?
* 요소 크기를 ___'어떻게 결정할것인지'___ 를 결정하는 속성

* html에서 요소는 한 가지만 갖는다.

* 대부분의 요소는 `inline` 혹은 `block` 요소를 가지고 있다.

* 그 외: `inline-block`, `flex`, `list-item`, `none`...
<br/><br/>

## 🖥 대표적인 display 속성값 네 가지
* ___none___
* ___block___
* ___inline___
* ___inline-block___

~원래는 16가지나 되지만~ 위 4가지가 가장 자주 사용된다.
<br/><br/>

## ⌨️ (1) display : none
* 화면에서 사라진다.

* 크기도 차지하지 않는다.
<br/><br/>

## ⌨️ (2) display : block
* 기본적으로 `width`가 자신의 컨테이너의 100%로 설정되어 있다.

* 쉽게 말해서 가로로 한 줄을 다 차지한다.

* `width`와 `height`, `margin`과 `padding`값을 지정해 줄 수 있다.

* 줄바꿈이 자동으로 이루어진다.

* (`block` 요소와 `margin: 0 auto` 가 만나면 중앙정렬 끄읕)

* 대표적인 block 태그: `<div>`, `<p>`, `<header>`, `<footer>`, `<ul>`, `<li>`, `<h1>`. . .
<br/><br/>

## ⌨️ (3) display : inline
* 컨텐츠의 크기만큼만 차지한다.

* `block` 태그와 다르게 줄바꿈이 안된다.

* 반드시 컨텐츠를 감싸게 되고, 크기(`width`, `height`)를 변화시킬 수 없다.

* `height`도 폰트 크기와 같게 설정된다.

* `margin`은 위아래엔 적용되지 않는다.

* `padding`은 좌우는 공간과 시각적인 부분이 모두 적용되는 반면, 위아래는 시각적으로는 추가되지만 공간은 차지하지 않는다.

* 대표적인 inline 태그: `<span>`, `<a>`, `<b>`, `<i>`, `<img>`, `<button>`
* <br/><br/>

## ⌨️ (4) display : inline-block
* `inline`과 `block`의 특성을 합쳐놓은 속성이다.

* 줄바꿈이 이루어지지 않는다.

* `block`처럼 `width`와 `height`를 지정할 수 있다.

* 만약 크기를 지정하지 않을 경우, `inline`처럼 컨텐츠만큼 영역이 잡힌다.

* (Explorer 7 이하에서는 사용할 수 없다.)
<br/><br/><br/>

***
## 참고
* [devCecy - [HTML/CSS]Display 속성](https://velog.io/@cecy-coding/HTML-CSS-Display-%EC%86%8D%EC%84%B1)
* [guitarlove00.log - [TIL]position, display, float 속성 정리](https://velog.io/@guitarlove00/position-display-float-%EC%86%8D%EC%84%B1-%EC%A0%95%EB%A6%AC)
* [bjls00.log - display 속성](https://velog.io/@bjls00/Codeit1)
* [개발자 아저씨들 힘을모아 - [CSS] display란? / display 속성 / display 종류 / 🖼](https://programming119.tistory.com/97)
