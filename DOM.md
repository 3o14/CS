# .__.) DOM을 조작해보자!
### DOM으로 HTML 요소를 자바스크립트 객체처럼 조작하자
<br/>

## 🖥 DOM?
* Document Object Model = 문서 객체 모델

* HTML 요소를 자바스크립트 객체(Object)처럼 조작할 수 있게 만든 모델/구조

* 즉, DOM을 이용해서 HTML로 구성된 웹페이지를 동적으로 움직이게 만들 수 있다
<br/><br/>

## 🖥 DOM에서 사용되는 CRUD 메소드
document 객체의 다음 메소드들을 사용해서 HTML 요소들을 조작할 수 있다.

* __C__ REATE: `createElement`

* __R__ EAD: `querySelector`, `querySelectorAll`, `getElementById`, `getElementByClassName`

* __U__ PDATE: `textContent`, `id`, `classList`, `setAttribute`

* __D__ ELETE: `remove`, `removeChild`, `innerHTML=""`, `textContent=""`

* cf) APPEND: `appendChild`
<br/><br/>

## ⌨️ CREATE 요소 생성
### 1. createElement
* 요소를 추가한다.

```js
document.createElemtent('newDiv')
```

## ⌨️ READ 요소 조회
### 1. querySelector
* document.querySelector() 는 입력한 선택자와 일치하는 문서 내의 첫 번째 element를 반환한다.

* 일치하는 요소가 없다면 null을 반환한다.

* 괄호 안에 들어가는 매개변수는 유효한 CSS 선택자여야한다.

```js
document.querySelector("p");
document.querySelector(".ginger");
document.querySelector("#Lee");
```

### 2. querySelectorAll
* querySelector()가 한 개의 요소를 반환했다면, querySelectorAll()은 주어진 CSS 선택자와 일치하는 모든 요소를 반환한다.

* 이때, 반환 타입은 리스트 타입이다.

* 따라서 인덱스를 통해 조작할 수 있다.

* (get으로 시작하는 DOM 메소드는 비교적 옛날 방식)

```html
<p class="test">test1</p>
<p class="test">test2</p>
<p class="test">test3</p>
```

```js
let test = document.querySelectorAll(".test");

function testFunc() {
  let i;
  for (i = 0; i < test.length; i++) {
    test[i].innerHTML = i;
  }
}
```

### 3. getElementById
* id를 통해 엘리먼트를 반환한다.

* 만약 document에 구체적인 ID의 엘리먼트가 없다면 null을 반환한다.

```html
<div id="parent">
    <div id="child">
        Hello, world!
    </div>
</div>
<script>
    var child = document.getElementById("child");
    child.style.color="blue";
</script>
```

### 4. getElementByClassName
* getElementByClassName을 사용하면 태그의 이름(name) 속성값으로 노드에 접근이 가능하다.

* 이때, 반환 타입은 리스트 타입이다.

* (getElementByTagName 도 동일)

```html
<input type='text' name='textName'/>
<input type='text' name='textName'/>
```

```js
// name이 'textName'인 모든 노드를 찾아 배열로 반환한다.
const textBoxList = document.getElementByName("textName");
for(textBox of textBoxList) {
  textBox.value = 'Hello World';
}
```

## ⌨️ UPDATE 요소 변경
### 1. innerText
* 자바스크립트에서 요소(element)에 텍스트를 추가하거나 값을 가져올 수 있다.

  ### _🖐🏻 잠깐! textContent와의 차이는? - textContent VS innerText_
  * textContent가 먼저 만들어지고 더 빨리 사용됨 -> 브라우저 호환성이 더 높음
  * textContent가 조금 더 가벼움
  * 연속된 스페이스 공백이 있을 경우 innerText-하나의 공백만, textContent-연속된 공백 그대로 가져옴
   
### 2. innerHTML
* 요소(element)의 내용을 변경할 수 있다.

* [innerHTML](https://github.com/3o14/CS/blob/main/JavaScript/Syntax2.md#1-%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%91%9C%EC%8B%9C-%EB%B0%A9%EB%B2%95)

```js
document.getElementById("id 이름").innerHTML = 변경하고 싶은 내용


const content = element.innerHTML;

element.innerHTML = htmlString;
```

* 요소의 내용 변경이 아니라 HTML을 document에 삽입하려면, `insertAdjacentHTML(..)` 메서드를 사용하기

* 일반 텍스트를 삽입할 때는 `innerHTML` 대신, `Node.textContent`를 사용하기 (보안위험)

### 3. classList
* Element.classList는 엘리먼트의 클래스 속성의 컬렉션인 활성 DOMTokenList를 반환하는 읽기 전용 프로퍼티이다.

* classList 사용은 공백으로 구분된 문자열인 element.className을 통해 엘리먼트의 클래스 목록에 접근하는 방식을 대체하는 간편한 방법이다.

* __메서드__
#### `add( String [, String [, ...]] )`
  * 지정한 클래스 값을 추가한다.
  * 만약 추가하려는 클래스가 엘리먼트의 class 속성에 이미 존재한다면 무시한다.

#### `remove( String [, String [, ...]] )`
  * 지정한 클래스 값을 제거한다.
  * (존재하지 않는 클래스 제거를 시도해도 에러는 일어나지 않음)

#### `item( Number )`
  * 콜렉션의 인덱스를 이용하여 클래스 값을 반환한다.

#### `toggle( String [, force] )`
  * 하나의 인수만 있을 때: 클래스 값을 토글링한다. 즉, 클래스가 존재한다면 제거하고 false를 반환하며, 존재하지 않으면 클래스를 추가하고 true를 반환한다.
  * 두번째 인수가 있을 때: 두번째 인수가 true로 평가되면 지정한 클래스 값을 추가하고 false로 평가되면 제거한다.

#### `contains( String )`
  * 지정한 클래스 값이 엘리먼트의 class 속성에 존재하는지 확인한다.

#### `replace( oldClass, newClass )`
  * 존재하는 클래스를 새로운 클래스로 교체한다.

```js
const div = document.createElement('div');
div.className = 'foo';

// 현재상태 : <div class="foo"></div>
console.log(div.outerHTML);

// classList 메소드를 이용하여 클래스 삭제 및 생성하기
div.classList.remove("foo");
div.classList.add("anotherclass");

// 현재상태 : <div class="anotherclass"></div>
console.log(div.outerHTML);

// 토글 메서드 -> 만약 visible 상태라면 삭제하고, 아니라면 생성한다.
div.classList.toggle("visible");

// 토글 메서드 -> depending i 가 10 이하
div.classList.toggle("visible", i < 10 );

console.log(div.classList.contains("foo"));

// 여러개의 클래스 생성 및 제거
div.classList.add("foo", "bar", "baz");
div.classList.remove("foo", "bar", "baz");

// 여러 개의 클래스 생성 및 제거 by using spread syntax
const cls = ["foo", "bar"];
div.classList.add(...cls);
div.classList.remove(...cls);

// 클래스 "foo"를 "bar"로 교체하기
div.classList.replace("foo", "bar");
```

### 4. setAttribute
* 요소(element)의 속성(attribute)을 추가할 수 있다.

```js
element.setAttribute( '속성명(예:color)' , '속성값(예:red)' );
```

## ⌨️ DELETE 요소 삭제
### 1. remove
* 요소(element)를 삭제하는 메서드

```html
<div id="div-01">Here is div-01</div>
<div id="div-02">Here is div-02</div>
<div id="div-03">Here is div-03</div>
```

```js
const element = document.getElementById('div-02');
element.remove(); // id가 'div-02'인 div를 삭제한다.
```

### 2. removeChild
* 자식 엘리먼트를 지정해서 삭제한다.

```html
<div id="top">
  <div id="nested"></div>
</div>
```

* 부모 노드를 알고 있을 때 특정 요소(element) 제거하기
```js
let d = document.getElementById("top");
let d_nested = document.getElementById("nested");
let throwawayNode = d.removeChild(d_nested);
```

* 부모 노드를 모를 때 특정 요소(element) 제거하기
```js
let node = document.getElementById("nested");
if (node.parentNode) {
  node.parentNode.removeChild(node);
}
```

* 요소(element)의 모든 자식 삭제하기
```js
let element = document.getElementById("top");
while (element.firstChild) {
  element.removeChild(element.firstChild);
}
```

### 3. innerHTML=""
* 자식 엘리먼트를 삭제한다.

* (보안상 문제가 많은 방법)

```js
document.querySelector('#container').innerHTML = ' ';
```

### 4. textContent=""
* innerHTML과 사용법은 같다.
<br/><br/>

## ⌨️ APPEND
### 1. append
```js
append(param1)
append(param1, param2)
append(param1, param2, /* ... ,*/ paramN)
```

* node 객체나 문자열 객체를 요소(element)의 마지막 자식(child)으로 삽입할 수 있는 메서드

* ruturn값을 가지지 않는다.

* 복수의 객체 삽입할 수 있다.

---

* 요소(element)를 삽입할 때
```js
let div = document.createElement("div")
let p = document.createElement("p")
div.append(p)

console.log(div.childNodes) // NodeList [ <p> ]
```

* 텍스트(text)를 삽입할 때
```js
let div = document.createElement("div")
div.append("Some text")

console.log(div.textContent) // "Some text"
```

* 요소(element)와 텍스트(text)를 삽입할 때
```js
let div = document.createElement("div")
let p = document.createElement("p")
div.append("Some text", p)

console.log(div.childNodes) // NodeList [ #text "Some text", <p> ]
```

### 2. appendChild
* 노드만 추가할 수 있다.

* ruturn값을 가진다.

* 복수의 객체 삽입할 수 없다.

```js
// 새 요소(element) p를 생성하고 body의 마지막 부분에 자식으로 삽입한다.
let p = document.createElement("p");
document.body.appendChild(p);
```
<br/><br/>

## 🖥 JavaScript로 HTML 요소 생성하기
### 1. 새로운 div 요소를 생성한다.
```js
const nameDiv = document.createElement("div");
console.log(nameDiv); // <div></div>
```

### 2. 아직 빈 상태인 div 요소에 textContent를 사용해서 내용 추가한다.
```js
nameDiv.textContent = "Jiho";
console.log(nameDiv); // <div>Jiho</div>
```

### 3. 스타일이 적용되어 있는 임의의 클래스 student가 있다고 가정하고, nameDiv 요소에 클래스 추가한다.
```js
nameDiv.classList.add("student");
console.log(nameDiv); // <div class="student">Jiho</div>
```

### 4. 마지막으로, 생성된 요소를 원하는 요소(document.body)에 append()를 이용해서 추가한다.
```js
document.body.append(nameDiv);
```

### cf) setAttribute() 메소드로 class, id 외의 속성 추가하기

* 사용 예) nameDiv.setAttribute(속성이름, 속성값)
* 해당 속성이 이미 존재하면 값이 변경되고, 없으면 새로 추가된다.
* `removeAttribute()`를 이용하면 요소의 속성을 삭제할 수 있다.
<br/><br/>

## 🖥 JavaScript로 HTML 요소 삭제하기
### 방법1: 삭제하려는 요소의 위치를 참조할 수 있는 경우
- studentList 요소 아래에 nameDiv를 추가했다가 remove로 삭제하는 예제
```js
const studentList = document.querySelector("#studentList"); 
const nameDiv = document.createElement("div"); studentList.append(nameDiv); 
nameDiv.remove();
```

### 방법2: 여러 개의 자식 요소를 지우고 싶은 경우
- `innerHTML`을 사용해서 studentList에 포함된 내용을 모두 삭제하는 예제
```js
document.querySelector("#studentList").innerHTML = "";
```

⚠️ 단, 이 경우에 보안상 문제가 생길 수 있기 때문에 다음 방법들을 사용하는 것을 고려해보는 것이 좋다:
- `Element.setHTML()` 사용해서 DOM에 넣기 전에 텍스트를 삭제(sanitize)한다.
- `Node.textContent`를 사용하면 입력된 문자열을 HTML로 파싱하지 않고 플레인텍스트로 삽입하기 때문에 더 안전하다.
- `removeChild` 메소드로 요소를 삭제한다.

### 방법3: removeChild를 이용한 자식 요소 삭제
- 자식 요소가 남아있지 않을 때까지 반복문(while문)을 돌면서 첫 번째 자식 요소를 삭제한다.
```js
const container = document.querySelector('#container'); 
while (container.firstChild) {
  container.removeChild(container.firstChild); 
}
```
<br/><br/><br/>

***
## 참고
* [MDN - JavaScript](https://developer.mozilla.org/ko/docs/Web/API/Element/innerHTML)
* [bokjiho - [JavaScript]DOM으 HTML 요소 조작하기](https://bokjiho.medium.com/javascript-dom%EC%9C%BC%EB%A1%9C-html-%EC%9A%94%EC%86%8C-%EC%A1%B0%EC%9E%91%ED%95%98%EA%B8%B0-49959216c493)
* [isthisit - JavaScript - DOM 조작 방법](https://is-this-it.tistory.com/56)
* [hianna - [JavaScript] innerHTML, innerText, textContent](https://hianna.tistory.com/483)
* [개발에 AtoZ까지 - [ES6][JS]DOM 객체 CRUD 하는 방법](https://atoz-developer.tistory.com/101)
* [하루 한발씩 개발자로 - DOM CRUD(코드스테이츠)](https://jesstory-codinglish.tistory.com/9)


