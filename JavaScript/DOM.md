# 미완_으
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


## ⌨️ JavaScript로 HTML 요소 생성하기
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

## ⌨️ JavaScript로 HTML 요소 삭제하기
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
<br/><br/>

## ⌨️ JavaScript로 HTML 요소 찾기
* document.getElementById("아이디"): 요소 ID로 요소 찾기
* document.getElementByTagName("태그 이름"): 태그 이름으로 요소 찾기
* document.getElementByClassName("클래스 이름"): 클래스 이름으로 요소 찾기
document.querySelectorAll("선택자"): CSS 선택자 전부 찾기
document.querySelector("선택자"): CSS 선택자 중 첫 번째 하나만 찾기


<br/><br/><br/>

***
## 참고
* [bokjiho - [JavaScript]DOM으 HTML 요소 조작하기](https://bokjiho.medium.com/javascript-dom%EC%9C%BC%EB%A1%9C-html-%EC%9A%94%EC%86%8C-%EC%A1%B0%EC%9E%91%ED%95%98%EA%B8%B0-49959216c493)
* [isthisit - JavaScript - DOM 조작 방법](https://is-this-it.tistory.com/56)
* 


