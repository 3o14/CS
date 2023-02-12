# ._.) 폼(Form)이란 무엇일까?
### 폼, 입력 폼은 클라이언트가 정보를 입력, 선택하고, 웹 서버 등의 폼을 처리하는 에이전트로 제출하기 위한 기구이다.
<br/>

```
<body>
    <form action="" method="" enctype="">
        <input type="text" name="test"> <br><br>
        <input type="submit">
    </form>
</body>
```

<br/>
HTML의 폼은 위의 코드와 같이 클라이언트에게 보낼 Input 태그를 감싸는 형태로 작성된다.

* `action` : 데이터를 받아서 보낼 url 주소를 정한다. 

* `method` : 데이터를 GET,POST,PUT...어떤 방식으로 보낼지 정한다.

* `enctype` : 데이터의 인코딩 방식을 정한다.

이렇게 form은 자신의 태그 안에 있는 input 태그들의 정보들을 모아 action에 설정된 url로 method에 정의된 방식으로 데이터를 enctype에 따라 보내게 된다.
<br/><br/>

## 🖥 폼이란 무엇일까?

* 폼이란, 사용자가 정보를 입력, 선택할 때 사용되는 태그이다.

* HTML에서의 Form은 사용자가 웹사이트에 데이터를 전송하는 것을 허용한다.

* → 텍스트 필드, 셀렉 박스, 버튼, 체크 박스 등의 역할을 수행할 수 있다.
<br/><br/>

## ._.) input 속성의 type 종류

1. __`text`__ : 한줄로 된 input을 정의한다.

2. __`Radio button`__ : 사용자가 선택지에서 한가지만 선택할 수 있다.

3. __`submit`__ : form 데이터를 서버로 submit해주는 역할.
<br/><br/>

## ._.) button 속성의 type 종류

1. __`submit`__ : 폼 데이터를 `<form>` 요소의 action 속성에 정의된 웹페이지로 전송한다.

2. __`reset`__ : 모든 폼 위젯을 기본 값으로 바꾼다.

3. __`button`__ : 기본 행동이 없으며, 클릭했을 때 아무것도 하지 않는다.
<br/><br/>

## 🖥 유효성 검사란 무엇일까?
* 유효성 검사란?

   form의 유효성 검사란 서버로 데이터를 제출하기 전, 포함되어야 할 정보들이 올바른 형식이고, 입력 조건에 맞게 잘 입력되었는지 확인하는 것이다.

* → 회원가입 시 아이디, 비밀번호, 이메일 주소 등을 입력하도록 하는 것

* → 비밀번호 입력 시 문자, 숫자, 기호 조합 8자리 이상 지정하도록 하는 것
<br/><br/><br/>

***
## 참고
* [brogod.log - 폼과 유효성 검사](https://velog.io/@m-vault/%ED%8F%BC%EA%B3%BC-%EC%9C%A0%ED%9A%A8%EC%84%B1-%EA%B2%80%EC%82%AC)
* [goban.log - HTML폼과 유효성검사](https://velog.io/@goban/HTML%ED%8F%BC%EA%B3%BC-%EC%9C%A0%ED%9A%A8%EC%84%B1%EA%B2%80%EC%82%AC)
* [땅다람쥐의 나날 - 폼(Form)과 유효성 검사](https://gopher-cs.tistory.com/6)
