<br>

# Symbol 타입

## 1. Symbol이란
ES6에서 새롭게 추가된 7번째 타입으로 변경 불가능한 원시 타입의 값이며, 주로 이름의 충돌 위험이 없는 유일한 객체의 프로퍼티 키(property key)를 만들기 위해 사용됨

<br>

## 2. Symbol의 특징
- 객체 속성(object property)을 만들 수 있는 원시 데이터 형식(primitive data type)이다.
- Symbol 의 valueof 는 원시형 값이 아니다. 때문에 문자형과 합칠수 없다.
- Symbol() 함수는 `String`, `Number`, `Boolean`과 같이 래퍼 객체를 생성하는 생성자 함수와는 달리 new 연산자를 사용하지 않는다.

<br>

## 3. Symbol의 생성
```javaScript
Symbol();
Symbol.for();
Symbol.iterator
```
##### Symbol.iterator은 iterator 객체를 정의하기 위해 쓰임
<br>

```javaScript
var sym1 = Symbol();
var sym2 = Symbol("foo");
var sym3 = Symbol("foo");
```
##### 세 개의 새 심볼을 생성
<br>

#### <span style="color:red">유의사항 : Symbol("foo")는 "foo"라는 문자열을 심볼로 강제로 변환시키지 않는다. 매법 새로운 심볼을 생성한다.</span>
<br>

```javaScript
Symbol("foo") === Symbol("foo"); // false
```
```javaScript
var sym = new Symbol(); // TypeError
```

<br>

## 4. Symbol의 사용

```javaScript
const obj = {};

const mySymbol = Symbol('mySymbol');
obj[mySymbol] = 123;

console.log(obj); // { [Symbol(mySymbol)]: 123 }
console.log(obj[mySymbol]); // 123
```
##### Symbol 값을 객체의 프로퍼티 키로 사용할 수 있다. Symbol 값은 유일한 값이므로 <span style="color:skyblue">**Symbol 값을 키로 갖는 프로퍼티는 다른 어떠한 프로퍼티와도 충돌하지 않는다.**</span>

<br>

## 4. Symbol의 속성

#### `Symbol.length` : 값이 0인 길이 속성
#### `Symbol.prototype` : `Symbol` 생성자의 프로토타입을 나타냄

<br>

|반복 심볼|정규표현식 심볼|그 외 심볼|
|:---:|:---:|:---:|
|`Symbol.iterator`|	`Symbol.match`|`Symbol.hasInstance`|
|`Symbol.asyncIterator`|`Symbol.replace`|`Symbol.isConcatSpreadable`|
||`Symbol.search`|`Symbol.unscopables`|
||`Symbol.split`|`Symbol.species`|
|||`Symbol.toPrimitive`|
|||`Symbol.toStringTag`|

> [Symbol의 속성 더 자세히 확인하기](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Symbol)