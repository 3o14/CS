# ._.) concat을 배워보자.
### 불변성을 지키는 배열 추가
<br/>

## 🖥 concat() 

인자로 주어진 배열이나 값들을 기존 배열에 ___합쳐서 새 배열을___ 반환한다.

* 기존배열을 변경하지 않는다. -> 불변성을 위배하지 않음

* 추가된 새로운 배열을 반환한다.

<br/>

### ⌨️ 사용법
```js
배열.concat(복사할 배열);
```

### ⌨️ 사용예
```js
const array1 = ['a', 'b', 'c'];
const array2 = ['d', 'e', 'f'];
const array3 = array1.concat(array2);

console.log(array3);
// expected output: Array ["a", "b", "c", "d", "e", "f"]
```
