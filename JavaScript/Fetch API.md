# ._.) Fetch()함수를 배워보자!
### 자바스크립트 fetch API를 이용하여 비동기 HTTP 요청을 보낼 수 있다.
### API를 호출하고 데이터를 받는 방법을 알아보자.
<br/>

## 📌 요약
- __`fetch`함수를 사용하면 리소스를 비동기로 요청할 수 있다.__

- __`fetch`를 호출하면 브라우저는 요청을 보내고 `Promise` 객체를 반환한다.__
  - 요청이 완료되면 성공 여부에 상관없이 `Promise`가 `resolved` 되어 `Response` 객체가 반환된다.
  - (`404`, `500` 같은 경우와 같은 응답 코드를 받은 경우는 에러를 일으키지 않는다.)

- __HTTP 요청이 완료되지 못한 상태라면 `Promise`가 `rejected` 된다.__
  - 이 경우 `catch` 메서드를 사용하여 에러를 처리할 수 있다.
  - (네트워크 문제 및 존재하지 않는 사이트에 대한 요청에 해당한다.)

- __`Response` 객체는 응답에 대한 정보를 담고 있다.__
  - `ok`, `status` 속성을 이용하여 응답 성공 여부를 확인할 수 있다.

<br/>

### _🖐🏻 잠깐! 여기서 비동기란? - 동기적 vs 비동기적_
* 동기적 처리(Synchronous)
  
  * 코드가 위에서 아래로 순서대로 실행이 되는 것
  
  * 즉, 지금 진행하는 작업이 끝이나면 다른 작업으로 넘어가고 그 작업이 끝이 나면 다른 작업으로 넘어가는 방식

* 비동기적 처리(asynchronous)
  
  * 한번에 여러개가 진행되는 것
  
  * 주로 api요청, 파일읽기, 암호화, 복호화 등에서 자주 사용된다.

  * 비동기적 처리를 사용하는데 주로 사용되는 함수와 문법으로는 `callback` 함수와 `Promise`, `async/await` 문법 등이 존재한다.
<br/><br/>

## 🖥 fetch() 함수 기본
```js
fetch('api 주소')
  .then(res => res.json())
  .then(res => {
    // data를 응답 받은 후의 로직
  });
```

```js
fetch(url, options)
  .then((response) => console.log("response:", response))
  .catch((error) => console.log("error:", error));
```
* `fetch()` 함수는 첫번째 인자로 URL, 두번째 인자로 옵션 객체를 받고, Promise 타입의 객체를 반환한다.

* 반환된 객체는, API 호출이 성공했을 경우에는 응답(response) 객체를 resolve

* 실패했을 경우에는 예외(error) 객체를 reject한다.

* 옵션(options) 객체에는 HTTP 방식(method), HTTP 요청 헤더(headers), HTTP 요청 전문(body) 등을 설정해줄 수 있다.

* 응답(response) 객체로 부터는 HTTP 응답 상태(status), HTTP 응답 헤더(headers), HTTP 응답 전문(body) 등을 읽어올 수 있다.
<br/><br/>

## 🖥 GET 호출
```js
fetch("https://jsonplaceholder.typicode.com/posts/1")
.then((response) =>
  console.log(response)
)
.catch(err => {
    // error 처리
    console.log('Fetch Error', err);
});
```
  
* 요청이 성공할 경우 `then`에서 `response` 객체를 받아 처리하고 최종적으로 그 결과를 출력한다.

* 요청이 완료되지 못해 에러가 발생하면 `catch`에서 처리한다.

```js
Response {status: 200, ok: true, redirected: false, type: "cors", url: "https://jsonplaceholder.typicode.com/posts/1", …}
```
* 응답 객체를 통해 응답 상태가 200 OK인 것을 금방 알 수 있다.

```js
fetch("https://jsonplaceholder.typicode.com/posts/1")
  .then((response) => response.json())
  .then((data) => console.log(data));
```
* 대부분의 `REST API`들은 `JSON` 형태의 데이터를 응답하기 때문에, 응답(response) 객체는 `json()` 메서드를 제공한다.

```js
{
  "userId": 1,
  "id": 1,
  "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
  "body": "quia et suscipit↵suscipit recusandae consequuntur …strum rerum est autem sunt rem eveniet architecto"
}
```
* 이 메서드를 호출하면, 응답(response) 객체로 부터 JSON 포멧의 응답 전문을 자바스크립트 객체로 변환하여 얻을 수 있다.

* 단순히 특정 API에 저장된 데이터를 보여주는 웹페이지나 애플리케이션에서는 GET 방식의 HTTP 통신으로 충분함
<br/><br/>

## 🖥 POST 호출

원격 API에서 관리하고 있는 데이터를 생성해야 한다면 요청 전문을 포함할 수 있는 POST 방식의 HTTP 통신이 필요하다.

```js
fetch("https://jsonplaceholder.typicode.com/posts", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    title: "Test",
    body: "I am testing!",
    userId: 1,
  }),
}).then((response) => console.log(response));
```

* 동일한 API를 대상으로 이번에는 새로운 포스팅를 생성하기 위해서 fetch() 함수를 사용해보자.

* `method` 옵션을 `POST`로 지정해주고, `headers` 옵션을 통해 JSON 포멧을 사용한다고 알려줘야 한다.

* 요청 전문을 JSON 포멧으로 직렬화화여 가장 중요한 `body` 옵션에 설정해준다.

```js
Response {type: "cors", url: "https://jsonplaceholder.typicode.com/posts", redirected: false, status: 201, ok: true, …}
```

* 이번에는 응답 객체를 통해 응답 코드가 `201 Created`인 것을 알 수 있다.

```js
fetch("https://jsonplaceholder.typicode.com/posts", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    title: "Test",
    body: "I am testing!",
    userId: 1,
  }),
})
  .then((response) => response.json())
  .then((data) => console.log(data));
```

* 마찬가지 방법으로 응답 객체의 `json()` 메서드를 호출하면 응답 전문을 객체 형태로 얻을 수 있다.

```js
{title: "Test", body: "I am testing!", userId: 1, id: 101}
```

## 🖥 PUT, DELETE 호출
`GET`과 `POST`만큼은 아니지만, 원격 API에서 관리하는 데이터의 수정과 삭제를 위해서 `PUT`과 `DELETE` 방식의 HTTP 호출을 해야할 때가 있다.

* PUT 방식은 `method` 옵션만 `PUT`으로 설정한다는 점 빼놓고는 `POST` 방식과 매우 흡사하다.

```js
fetch("https://jsonplaceholder.typicode.com/posts/1", {
  method: "PUT",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    title: "Test",
    body: "I am testing!",
    userId: 1,
  }),
})
  .then((response) => response.json())
  .then((data) => console.log(data));
```

```js
{title: "Test", body: "I am testing!", userId: 1, id: 1}
```

* DELETE 방식에서는 보낼 데이터가 없기 때문에, `headers`와 `body` 옵션이 필요없다.

```js
fetch("https://jsonplaceholder.typicode.com/posts/1", {
  method: "DELETE",
})
  .then((response) => response.json())
  .then((data) => console.log(data));
```

```js
{}
```
<br/><br/><br/>

***
## 참고
* [MDN - Fetch 사용하기](https://developer.mozilla.org/ko/docs/Web/API/Fetch_API/Using_Fetch)
* [빠른손김참치 - [JS] 자바스크립트 fetch API 사용하기](https://hogni.tistory.com/142)
* [yeri-kim.github.io - fetch()함수 사용법](https://yeri-kim.github.io/posts/fetch/)
* [DaleSeo - [자바스크립트] fetch()함수로 원격 API 호출하기](https://www.daleseo.com/js-window-fetch/)
