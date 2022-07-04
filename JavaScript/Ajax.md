# ._.) ajax를 써보자
### 비동기로 리소스를 불러오는 또 다른 방법
<br/>

## 🖥 ajax란?
* Ajax: Asynchronous Javascript And XML

* 자바스크립트를 이용하여 비동기 식으로 서버와 통신을 한다.

* 비동기통신이기 때문에 서버에 요청이 가더라도 화면의 깜빡 거림이나 화면이 이동 된다는 느낌을 주지 않고 상당히 자연스럽고 빠르게 클라이언트의 화면을 변화 시켜준다.

* 최근에는 XML형식이 아닌 JSON형식을 더 많이 사용하고 있다.
<br/><br/>

### ⌨️ 장점
* 웹페이지 속도 향상

* 서버에서 처리가 완료될때까지 기다리지 않고 다른 프로세스를 진행할 수 있다.

* 비동기 방식이기 때문에 동기 방식과 다르게 UI를 변경할 수 있어서 장점이 된다.

### ⌨️ 단점
* 연속으로 데이터를 요청하면 서버 부하가 증가할 수 있다.

* 히스토리 관리가 안되므로 보안에 좀 취약하다.

* HTTP 클라이언트의 기능이 한정되어 있다.
<br/><br/>

## 🖥 ajax 사용해보기

```html
<!DOCTYPE html>
<html>
  <body>
    <h2 id="time_text">Boom</h2>
    <input type="button" id="ajax_button" value="버튼"/>
  </body>
  <script src="https://code.jquery.com/jquery-lastest.js"></script>
  
  <script>
    $("#ajax_button").click(()=>{
      $.ajax(
        {
          type: "GET", // 전송 방식
          url: "./ajax",
          data: {}, // 전송 파라미터
          dataType: "text", // 받아올 데이터타입(생략가능) html, json, xml 등
          success: (time)=>{$(#time_text).html(time)},
          error: (log)=>{alert("실패"+log)}
        }
      )
    })
  </script>
</html>
```

1. type은 get이나 post 같은 http method를 나타낸다.

2. url는 데이터를 받아올 페이지다. 이 페이지의 코드는 곧 설명하겠다.

3. data는 요청시에 함께 보낼 파라미터들이다. 난 그냥 안보낼거라 비워뒀다.

4. dataType은 받아올 데이터의 형식인데, 빼놔도 된다.

5. success는 성공시에 수행할 핸들러를 받는다.

6. error는 실패시에 수행할 핸들러를 받는다.

### ⌨️ ./ajax.js
```js
const express = require('express');
const router = express.Router();

/* GET home page. */
router.get('/', (req, res, next) => {
  res.send(new Date());
});

module.exports = router;
```
<br/><br/><br/>

***
## 참고
* [MDN web docs - Ajax 시작하기](https://developer.mozilla.org/ko/docs/Web/Guide/AJAX/Getting_Started)
* [記可為學 - [jQuery] ajax 사용법](https://m.blog.naver.com/sssang97/221640020197)
* [고똘이의 IT 개발이야기 - [Jquery] 제이쿼리 Ajax 설명 사용법 및 예제(간단)](https://dion-ko.tistory.com/59)
