<br>

# var, let, const

## 1. var

- ### 함수 레벨 스코프이다.(오로지 함수의 코드 블록만을 지역 스코프로 인정)

```javaScript
var name = 'bathingape'
    console.log(name) // bathingape

    var name = 'javascript'
    console.log(name) // javascript
```
- ### 변수를 한 번 더 선언 했음에도 에러가 나오지 않고 각기 다른 값이 출력된다.

- ### `var`으로 선언된 변수는 선언 단계와 초기화 단계가 한번에 이루어진다.

- ### 변수 선언시 초기 값을 주지 않으면 자동으로 `undifined`를 초기 값으로 하여 메모리를 할당한다.

- ### 따라서 `var`로 선언한 변수는 선언 전에 사용해도 에러가 나지 않는다.

- ### <span style="color:red">버그 발생과 메모리 누수의 위험 등이있다.</span>

<br>

## 2. let

- ### 블럭 레벨 스코프이다.(코드 블록 내부에서 선언한 변수는 지역 변수)

```javaScript
    let name = 'bathingape'
    console.log(name) // bathingape

    let name = 'javascript'
    console.log(name) 
    // Uncaught SyntaxError: Identifier 'name' has already been declared

    name = 'react'
    console.log(name) //react
```
- ### 변수에 재할당이 가능하다.

```javaScript
    // 스코프의 선두에서 선언 단계가 실행된다.
// 아직 변수가 초기화(메모리 공간 확보와 undefined로 초기화)되지 않았다.
// 따라서 변수 선언문 이전에 변수를 참조할 수 없다.

console.log(foo); // ReferenceError: foo is not defined

let foo; // 변수 선언문에서 초기화 단계가 실행된다.
console.log(foo); // undefined

foo = 1; // 할당문에서 할당 단계가 실행된다.
console.log(foo); // 1
```
- ### 이미 존재하는 변수와 같은 이름의 변수를 또 선언할 수 없으며, 선언 단계와 초기화 단계가 분리되어 진행된다.

- ### 변수 선언 시 초기 값을 주지 않아도 된다.

<br>

## 3. const

- ### 블럭 레벨 스코프이다.(코드 블록 내부에서 선언한 변수는 지역 변수)

```javaScript
    const name = 'bathingape'
    console.log(name) // bathingape

    const name = 'javascript'
    console.log(name) 
    // Uncaught SyntaxError: Identifier 'name' has already been declared

    name = 'react'
    console.log(name) 
    //Uncaught TypeError: Assignment to constant variable.
```
- ### 변수 재선언, 변수 재할당 모두 불가능하다.(단, 객체 안에 프로퍼티가 변경되는 것까지 막지는 못한다.)

- ### 반드시 초기값을 할당해야 한다.

- ### 변수 선언문 이전에 변수를 참조할 수 없다.