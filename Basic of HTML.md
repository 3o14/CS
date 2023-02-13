# ._.) HTML의 기초를 배워보자
### HTML - HyperText Markup Language

## 🖥 HTML이란?
* 웹 페이지를 만드는 마크업 언어

* 웹 페이지는 HTML 문서라고도 불림

* HTML 태그들로 구성됨

* 각각의 HTML 태그는 웹 페이지의 디자인이나 기능을 결정하는데 사용됨

### _🖐🏻 잠깐! 마크업 언어란? - 마크업 언어 (Markup Language)_
* 태그 등을 이용하여 문서나 데이터의 구조를 명기하는 언어의 한 가지
* 태그

  * 원래 텍스트와는 별도로 원고의 교정부호 및 주석을 표현하기 위한 것이었으나 용도가 점차 확장되어 문서의 구조를 표현하는 역할을 하게 됨

  * 문서의 골격에 해당하는 부분을 작성

* 일반적으로는 데이터를 기술하는 정도로만 사용되기 때문에 프로그래밍 언어와는 구분됨
* 예) HTML, XML, GenCode, troff/nroff, Tex, Scribe, GML, SGML
<br/><br/>

## 🖥 HTML 태그(tag)
* HTML 태그는 태그 이름을 꺾쇠 괄호(<>)로 감싸서 표현한다.

* HTML 태그는 보통 시작 태그(start tag, opening tag)와 종료 태그(end tag, closing tag)의 한 쌍이다.

* 시작 태그만 있고 종료 태그가 없는 태그도 있는데, 이를 빈 태그라고 한다.(empty tag)

<p align = center>
<img src="./img/스크린샷 2022-04-17 12.21.16.png">
</p>

### ._.) HTML 태그를 사용해보자

<p align=center>
<img src="./img/스크린샷 2022-04-17 12.00.40.png">
<img src="./img/스크린샷 2022-04-17 12.00.14.png" width=300px height=300px> 
</p>

### __1. `<html>`__

#### 웹페이지의 시작과 끝을 나타낸다.

### __2. `<head>`__

#### 웹 페이지의 정보, 문서에서 사용할 외부 파일들을 링크할 때 사용한다.

### __3. `<body>`__

브라우저에 실제 표시되는 내용을 담고있다.

### __4. `<title>`__

문서의 제목을 나타낸다. 웹브라우저의 제목 표시줄에 표시된다.

보통 제목표시줄이 더 많이 노출되기 때문에 잘 쓰면 좋다.

### __5. `<meta>`__

문자 인코딩 및 문서 키워드 요약 정보

```
<meta name="viewport" content="width=device-width, intitial-scale=1, user-scalable=no, maximum-scale=1, minimum-scale=1">
```
뷰포트란 화면상에 우리가 작성한 레이아웃이 나오는 전체 영역을 의미. 나중에 반응형 페이지를 위해서 뷰포트 세팅을 해줘야한다.

### __6. `<div>`__

아무런 의미가 없는 태그, 어떤 컨텐츠들을 목적에 따라 묶는 용도로 쓴다.

### __7. `<span>`__

div와 마찬가지로 아무런 의미가 없는 태그. div와 의 차이는 inline level element이기 때문에 span을 여러개 붙여도 줄바꿈이 되지 않는다.

### __8. `<a>`__

anchor, 웹페이지나 외부 사이트 연결

```
<a href="연결할 링크의 경로">링크이름</a>
```
하이퍼링크를 사용해서 페이지들간의 이동이 가능하다. 아직 다른페이지 준비가 안되있을 경우 "#"로 표시한다. 특정 id로 이동하는 앵커 역할도 할 수 있다.

### __9. `<script>`__

코드 삽입. 실행 가능한 코드를 참조하거나 삽입할 때 사용, 보통 자바스크립트 코드를 넣을 때 사용한다.

```
<script type="text/JavaScript">
  document.write("자바스크립트 코드 추가");
</script>
```

### __10. `<link>`__

외부 파일을 연결할 때 사용한다. css나 js 파일을 연결해서 쓴다.

```
<link rel="stylesheet" type="text/css" href="index.css"/>
```

### __11. `<img>`__

이미지 삽입, 웹페이지에 이미지를 넣을 때 사용한다.

### __12. `<p>`__

단락, 사용하면 내용 앞뒤로 빈 줄이 생기면서 단락이 생긴다.

### __13. `<li>`__

리스트 항목들을 나타내는데 사용

### __14. `<ul>`__

순서가 없는 리스트 항목을 묶음

### __15. `<ol>`__

순서가 있는 리스트 항목을 묶음

### __16. `<style>`__

head 안에서 스타일 정보를 정의할 때 사용하는 태그

### __17. `<br>`__

줄바꿈, 개행.

닫는태그가 필요 없다.

### __18. `<hn>h1 ~ h6`__

제목을 나타내는 태그

### __19. `<input>`__

form 의 요소중 하나 사용자가 정보를 입력할 때 쓰인다.

`<input type="유형" 속성="속성값">`

### __20. `<form>`__

get, post 방식으로 내용을 전송할 수 있다.

### __21. `<iframe>`__

외부 페이지를 삽입할 때 쓴다.

보통 동영상을 삽입하는 용도로 쓴다.

`<iframe src="삽입할 페이지 주소" [속성="속성값"]></iframe>`

```
<iframe 
        width="560" 
        height="315" 
        src="http://www.youtube.com/embed/VAoBIpxYfBE" 
        frameborder="0" 
        allow="autoplay; encrypted-media" 
        allowfullscreen>
</iframe>
```

### __22. `<strong>`__

중요한 내용 강조하는 태그

### __23. `<i>`__

이탤릭 체

### __24. `<button>`__

form 요소 중 하나로 페이지에 버튼을 넣고 form을 전송하거나 reset할 때 사용한다.

`type=submit`, `type=reset`이 있다.
<br/><br/>

***
## 참고
* [코딩의 시작 TCP School - HTML 기초](http://www.tcpschool.com/html/html_intro_basic)
* [bp.chys - HTML 기초 내용 정리](https://velog.io/@ljinsk3/HTML-%EA%B8%B0%EC%B4%88-%EB%82%B4%EC%9A%A9-%EC%A0%95%EB%A6%AC)
* [gptjs409 - Markup Language 마크업 언어란?](https://gptjs409.github.io/infra/2019/09/08/markup-language.html)
