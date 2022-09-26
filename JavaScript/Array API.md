# ._.) 유용한 배열 api 열가지를 알아보자.
<br/>

> 1. join
> 2. split
> 3. splice
> 4. reverse
> 5. find
> 6. filter
> 7. map
> 8. some, every
> 9. reduce
> 10. 함수형 프로그래밍 
 
<br/><br/>

## 🖥 1. join('구분자') - array를 string으로 변환
```js
// Q1. make a string out of an array
// A1. Array.join()  // join(separator?: string): string;
{
    const fruits = ['appale', 'banana', 'orange'];
    const result = fruits.join(', and '); // 구분자 넣기는 선택사항
    console.log(result);
}
 ```
<br/><br/>

## 🖥 2. split('구분자', 'limit') - string을 array로 변환
```js
// Q2. make an array out of a string
// A2. Array.split()  // split(separator: string | RegExp, limit?: number): string[];
{
    const fruits = '🍎, 🥝, 🍋, 🍉';
    const result = fruits.split(','); 
    console.log(result);
}
 ```
<br/><br/>

## 🖥 3. splice(start, end) - array에서 원하는 인덱스를 지정해 리턴받음
```js
// Q3. make this array look like this: [5,4,3,2,1]
// A3. Array.reverse()  // reverse(): T[]; 배열 자체를 reverse시킴
{
    const array = [1, 2, 3, 4, 5];
    const result = array.reverse();
    console.log(result);  // -> [5, 4, 3, 2, 1]
    console.log(array); // -> [5, 4, 3, 2, 1]   원본 array도 reverse된 상태
}
 ```
<br/><br/>

## 🖥 4. reverse( ) - array 요소의 순서를 거꾸로
```js
// Q4. make new array without the first two elements
// A4. Array.slice()  // slice(start?: number, end?: number): T[];
{
    const array = [1, 2, 3, 4, 5];
    const result = array.slice(2, 5);
    console.log(result); // -> [3, 4, 5]
    console.log(array); // -> [1, 2, 3, 4, 5] 변화 x
}

//=====

class Student {
    constructor(name, age, enrolled, score) {
        this.name = name;
        this.age = age;
        this.enrolled = enrolled;
        this.score = score;
    }
}

const students = [
    new Student('A', 29, true, 45),
    new Student('B', 28, false, 80),
    new Student('C', 30, true, 90),
    new Student('D', 40, false, 66),
    new Student('E', 40, true, 88),
];
```
<br/><br/>

## 🖥 5. find( )
```js
// Q5. find a student with the score 90
// A5. Array.find()  
// find<S extends T>(predicate: (this: void, value: T, index: number, obj: T[]) => value is S, thisArg?: any): S | undefined;
{
    console.clear();
    const result = students.find((student) => student.score === 90);
    console.log(result);
}
```
<br/><br/>

## 🖥 6. filter( )
```js
// Q6. make an array of enrolled students
// A6. Array.filter()  
// filter<S extends T>(predicate: (value: T, index: number, array: T[]) => value is S, thisArg?: any): S[];
{
    console.clear();
    const result = students.filter((student) => student.enrolled);
    console.log(result);
}
<br/><br/>
```

## 🖥 7. map(callbackfn) - 새로운 배열 생성
```js
// Q7. make an array containing only the students' scores
// result should be: [45, 80, 90, 66, 88]
// A7. Array.map()  // map<U>(callbackfn: (value: T, index: number, array: T[]) => U, thisArg?: any): U[];
{
    const result = students.map((student) => student.score);
    console.log(result);
}
```
<br/><br/>

## 🖥 8. some( ), every( ) - (boolean 값으로 리턴)
```js
// Q8. check if there is a student with the score lower than 50
// A8. Array.some()  // some(predicate: (value: T, index: number, array: T[]) => unknown, thisArg?: any): boolean;
{
    const result = students.some((student) => student.score < 50);
    console.log(result);    //some은 하나라도 조건에 부합하면 true

    const result2 =  students.every((student) => student.score >= 50);
    console.log(result2);    //every는 모든 요소가 조건에 부합해야 true
}
 ```
<br/><br/>

## 🖥 9. reduce( ) - 배열의 요소를 누적
```js
// Q9. compute students' average score
// A9. Array.reduce()  
// reduce(callbackfn: (previousValue: T, currentValue: T, currentIndex: number, array: T[]) => T): T;
{
    const result = students.reduce((prev, curr) => prev + curr.score, 0);
    console.log(result / students.length);
}
 ```
<br/><br/>

## 🖥 10. 함수형 프로그래밍 - 여러 메소드 동시에 사용 가능
```js
// Q10. make a string containing all the scores
// result should be: '45, 80, 90, 66, 88'
{
    const result = students
        .map((student) => student.score)
        .filter((score) => score >= 50)
        .join();
    console.log(result);
} // ㄴ> 함수형 프로그래밍
```
<br/><br/>

## 🖥 -BONUS QUIZ-   by using `sort( )`
```js
// Bonus! do Q10 sorted in ascending order
// result should be: '45, 66, 80, 88, 90'
// Array.sort()  // sort(compareFn?: (a: T, b: T) => number): this;
{
    const result = students
        .map((student) => student.score)
        .sort((a, b) => a - b)
        .join();
    console.log(result);
}
```
