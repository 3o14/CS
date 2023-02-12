# ._.)맵 Map을 배워보자.

## 🖥 맵(Map)이란?
* 맵(Map)은 키가 있는 데이터를 저장한다 => 객체와 유사

* 배열과의 차이점: 맵은 키에 다양한 자료형을 허용한다는 점에서 객체와 차이가 있다.

> * 객체 – 키가 있는 컬렉션을 저장함
> * 배열 – 순서가 있는 컬렉션을 저장함

<br/><br/>

## 🖥 맵(Map)의 주요 메서드 & 프로퍼티

* `new Map()` – 맵을 만듭니다.

* `map.set(key, value)` – key를 이용해 value를 저장합니다.

* `map.get(key)` – key에 해당하는 값을 반환합니다. key가 존재하지 않으면 undefined를 반환합니다.

* `map.has(key)` – key가 존재하면 true, 존재하지 않으면 false를 반환합니다.

* `map.delete(key)` – key에 해당하는 값을 삭제합니다.

* `map.clear()` – 맵 안의 모든 요소를 제거합니다.

* `map.size` – 요소의 개수를 반환합니다.

<br/> 

## ⌨️ 사용 예
```js
let map = new Map();

map.set('1', 'str1');   // 문자형 키
map.set(1, 'num1');     // 숫자형 키
map.set(true, 'bool1'); // 불린형 키

// 객체는 키를 문자형으로 변환한다는 걸 기억하고 계신가요?
// 맵은 키의 타입을 변환시키지 않고 그대로 유지합니다. 따라서 아래의 코드는 출력되는 값이 다릅니다.
alert( map.get(1)   ); // 'num1'
alert( map.get('1') ); // 'str1'

alert( map.size ); // 3
```

```js
let john = { name: "John" };

// 고객의 가게 방문 횟수를 세본다고 가정해 봅시다.
let visitsCountMap = new Map();

// john을 맵의 키로 사용하겠습니다.
visitsCountMap.set(john, 123);

alert( visitsCountMap.get(john) ); // 123
```
