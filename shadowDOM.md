# ._.) Shadow Dom에 대해서 알아봅시당
### 웹 컴포넌트의 캡슐화와 분리
<br/>

## 🍊 Shadow DOM이란?
Shadow DOM은 일반적인 DOM과 같지만 Shadow DOM 내부의 코드는 외부에 영향을 줄 수 없는 캡슐화를 허용한다는 점에서 다릅니다.

예를 들면, `<video>` 태그를 사용할 때 DOM에서 보여지는 것은 단순히 `<video>` 태그이지만 UI를 살펴보면 재생 버튼, 일시정지 버튼, progress bar 등 다양한 element가 있는 것을 볼 수 있습니다.

이러한 경우가 shadow DOM 내부에 각종 버튼들이 있는 것이라고 볼 수 있습니다.

### 🖐🏻 잠깐, 여기서 DOM이란?
* DOM은 Document Object Model의 약자로, 웹 페이지의 구조화된 표현을 나타내는 객체입니다.

* 웹 페이지의 요소를 트리 구조로 표현하며, 자바스크립트와 같은 스크립트 언어를 사용하여 웹 페이지의 요소를 선택하고 조작할 수 있습니다.

* DOM을 활용하여 웹 페이지의 내용, 구조, 스타일, 이벤트 등을 동적으로 조작할 수 있습니다.

<p align="center">
<img src="./img/shadowDom.svg">
</p>

<br/>

### 🥑 Shadow DOM 용어

 - Shadow host: Shadow DOM이 붙어 있는 일반적인 DOM 노드

 - Shadow tree: Shadow DOM 안에 있는 DOM 트리

 - Shadow root: Shadow tree의 루트 노드

 - Shadow boundary: Shadow DOM이 끝나고 일반 DOM이 시작되는 곳

<br/>

### 📍 Shadow DOM 확인하기
개발자 도구 -> 설정(톱니바퀴) -> Settings -> Elements -> Show user agent Shadow DOM

<br/><br/>

## 🍊 Shadow DOM 사용해보기

### ☑️ 생성한 Shadow DOM을 다른 요소에 부착하기
* `Element.attachShadow()` 메서드를 사용하여 어떠한 요소에든 shadow root을 부착할 수 있습니다.

* 이 메서드 `mode` 라는 옵션을 받으며 `open` 혹은 `closed` 의 값을 가집니다.

```js
let shadow = elementRef.attachShadow({mode: 'open'});
let shadow = elementRef.attachShadow({mode: 'closed'});
```


* `open` : 메인 페이지 맥락에서 작성된 JavaScript를 사용하여 shadow DOM에 접근할 수 있음을 의미
    * 예를 들자면 Element.shadowRoot (en-US) 속성을 사용하여 접근할 수 있습니다.

* `closed` : 외부로부터 shadow DOM에 접근할 수 없음을 의미
    * myCustomElem.shadowRoot 은 null 을 반환합니다.

<br/><br/>

## 🍊 예제를 통해 알아보기
![popupInfo_AdobeExpress](https://github.com/3o14/CS/assets/101818687/f31ad145-e7d8-44cb-b7c5-e74238731c3e)

input 왼쪽에 있는 아이콘이 focus될 떄, 팝업 정보 박스가 표시됩니다. 이 팝업 정보 박스를 ShadowDom으로 구현할 수 있습니다.

### ☑️ Shadow Dom 생성하기 

HTMLElement를 상속한 클래스를 PopUpInfo라고 정의하여 만들 수 있습니다.


```js
class PopUpInfo extends HTMLElement {
  constructor() {
    // 항상 super를 생성자에서 먼저 호출합니다
    super();

    // 요소 기능을 여기 작성합니다

    ...
  }
}
```

<br/>

### ☑️ shadow root 생성하기

먼저, shadow root을 위치시킬 다른 요소에 부착합니다.

```js
// shadow root을 생성합니다
let shadow = this.attachShadow({mode: 'open'});
```

v<br/>

### ☑️ shadow Dom 구조 생성하기
다음으로, 몇 가지 DOM 조작을 사용하여 요소의 내부 shadow DOM 구조를 생성합니다.

```js
// span들을 생성합니다
let wrapper = document.createElement('span');
wrapper.setAttribute('class', 'wrapper');
let icon = document.createElement('span');
icon.setAttribute('class', 'icon');
icon.setAttribute('tabindex', 0);
let info = document.createElement('span');
info.setAttribute('class', 'info');

// 특성의 내용을 취하고 그것을 info span 내부에 넣습니다
let text = this.getAttribute('data-text');
info.textContent = text;

// 아이콘을 삽입합니다
let imgUrl;
if(this.hasAttribute('img')) {
  imgUrl = this.getAttribute('img');
} else {
  imgUrl = 'img/default.png';
}
let img = document.createElement('img');
img.src = imgUrl;
icon.appendChild(img);
```

<br/>

### ☑️ shadow Dom 꾸미기

이후에 `<style>` 요소를 생성하고 shadow DOM을 꾸미기 위한 몇 가지 CSS로 style 요소를 채웁니다.

```css
// shadow DOM에 적용할 몇 가지 CSS를 생성합니다
let style = document.createElement('style');

style.textContent = `
.wrapper {
  position: relative;
}

.info {
  font-size: 0.8rem;
  width: 200px;
  display: inline-block;
  border: 1px solid black;
  padding: 10px;
  background: white;
  border-radius: 10px;
  opacity: 0;
  transition: 0.6s all;
  position: absolute;
  bottom: 20px;
  left: 10px;
  z-index: 3;
}

img {
  width: 1.2rem;
}

.icon:hover + .info, .icon:focus + .info {
  opacity: 1;
}`;
```

<br/>

### ☑️ shadow DOM을 shadow root에 부착하기

마지막으로 생성된 모든 요소를 shadow root에 부착합니다.

```js
// 생성된 요소들을 shadow dom에 부착합니다
shadow.appendChild(style);
shadow.appendChild(wrapper);
wrapper.appendChild(icon);
wrapper.appendChild(info);
```

<br/>

### ☑️ 사용자 정의 요소 사용하기
한 번 클래스가 정의되고 나면, 요소를 사용하는 것은 아주 간단합니다.

```js
// 새로운 요소를 정의합니다
customElements.define('popup-info', PopUpInfo);
```

```html
<popup-info img="img/alt.png" data-text="Your card validation code (CVC) is an extra
                                    security feature — it is the last 3 or 4
                                    numbers on the back of your card.">
```

오늘은 shadow DOM에 대해서 알아보았습니다.

<br/><br/><br/>
***

## 참고
* [shadow DOM 사용하기](https://developer.mozilla.org/ko/docs/Web/API/Web_components/Using_shadow_DOM)
* [[HTML] Shadow DOM 이란? (feat. 크롤링 실패)](https://sunghee2.tistory.com/entry/Shadow-Dom-%EC%9D%B4%EB%9E%80-feat-%ED%81%AC%EB%A1%A4%EB%A7%81-%EC%8B%A4%ED%8C%A8#toc2)
* [What is DOM, Shadow DOM and Virtual DOM?](https://www.youtube.com/watch?v=7Tok22qxPzQ)