## 

## 변수와 식별자

- 식별자(identifier)는 변수를 구분할 수 있는 변수명을 말함

- 문자, $, _ 로 시작

- 대소문자 구분, 클래스명 외에는 모두 소문자로 시작

- 예약어(for, if, function) 사용 불가능



## Declaration

- 변수를 생성하는 행위 또는 시점

```js
let foo    // 선언
console.log(foo) // undefined
```

## Assignment

- 선언된 변수에 값을 저장하는 행위, 시점

```js
foo=11    //할당
console.log(foo)    //11
```

## Initialization

- 선언된 변수에 처음으로 값을 저장하는 행위 또는 시점

```js
let bar = 0    // 선언 + 할당
console.log(bar)    // 0
```

> let ( 재할당 가능) const(재할당 불가능)



> let, const ( 재선언 불가능)



## 블록 스코프*( block scope on const,let)

- if, for 함수 등의 중괄호 내부

- 블록 바깥에서 접근 불가능

```js
let x = 1
if ( x === 1){
    let x =2
    console.log(x)      // 2
}


console.log(x)     // 1
```

## var

- var로 선언한 변수는 재선언, 재할당 모두 가능

- ES6 이전에 변수사용 키워드, 문제발생 가능성이 있으므로, ES6 이후론 const ,let 사용



```js
var number = 10 // 1. 선언 및 초기값 할당
var number = 50 // 2. 재할당

console.log(number)    //50

```



## Funtcion scope( on var)

- 함수 중괄호 내부

- 함수 바깥에서 접근 불가능

```js
let x = 1

if ( x === 1){
    let x = 2
    console.log(x)    // 2
}

console.log(x)         // 1
```

## Hoisting

- 변수를 선언 이전에 참조할 수 있는 현상

- 변수 선언 이전의 위치에서 접근시 undefined를 반환

- javascript는 모든 선언을 호이스팅한다.

- var, let, const 모두 hoisting이 발생하지만 var은 선언과 초기화가 동시에 발생하여 일시적 사각지대가 존재하지 않는다.

| 키워드   | 재선언 | 재할당 | 스코프            | 비고         |
|:-----:|:---:|:---:|:--------------:|:----------:|
| let   | X   | O   | block scope    | after ES6  |
| const | X   | X   | block scope    | after ES6  |
| var   | O   | O   | Function scope | before ES6 |

## Data type

- 자바스크립트의 모든 값은 특정한 데이터 타입을 가짐

- Primitive type, Reference type 으로 분류

## Primitive type

- 객체가 아닌 기본타입

- 변수에 해당 타입의 값이 담김

- 다른 변수에 복사할 때  실제 값이 복사됨

## Reference type

- 객체 타입의 자료형

- 변수에 해당 객체의 참조 값이 담김

- 다른 변수에 복사할 때 참조 값이 복사됨

## Number

- 정수, 실수 구분없는 하나의 숫자 타입

- 부동소수점 형식

- NaN ( Not-A-Number)
  
  - 계산 불가능한 경우 반환되는 값



## String

- 텍스트 데이터를 나타내는 타입

- 16비트 유니코드

- 작은 따옴표, 큰따옴표 모두 가능



## undefined

- 변수의 값이 없음을 나타내는 데이터 타입

## NULL

- 변수의 값이 없음을 의도적으로 표현할 때 사용

- null, typeof
  
  - typeof 연산자의 결과는 객체(object)로 표현됨

## Boolean

- 논리적 참, 거짓을 나타내는 타입

- True, False

- 조건문,반복문에서 유용하게 사용



| Data type | False        | True            |
| --------- | ------------ | --------------- |
| Undefined | Always False | X               |
| Null      | Always False | X               |
| Number    | 0, -0, NaN   | all other cases |
| String    | Empty        | all other cases |
| Object    | X            | Always True     |

## 연산자

- 할당연산자
  
  - 오른쪽에 있는 결과를 왼쪽 피연산자에 할당
  
  - (++) = 피연산자의 값을 1 증가시키는 연산자
  
  - (--) = 피연산자의 값을 1 감소시키는 연산자
  
  - += , -= 표현 권장

- 비교연산자
  
  - 결과값을 boolean으로 반환
  
  - 문자열은 유니코드기반, 표준 사전 순서 비교

- 동등 비교 연산자(==)
  
  - boolean으로 값 반환
  
  - 특별한 경우 제외 사용하지 않음

- 일치 비교 연산자(===)
  
  - 비교 후 boolean 반환
  
  - 염격한 비교 발생

- 논리 연산자
  
  - and 연산은 &&
  
  - or 연산은 ||
  
  - not 연산은 !
  
  - 단축 평가 지원
    
    - false && true ==>> false
    
    - True || false ==>>True

- 삼항 연산자
  
  - 세 개의 피연산자를 사용하여 조건에 따라 값을 반환하는 연산자
  
  - 가장 왼쪽의 조건식이 참이면 : 앞의 값, 그렇지 않으면 :의 뒤의 값 사용
  
  - 변수 할당 가능
  
  - 한 줄에 표시하는 것 권장

## 조건문

- if
  
  - 결과값을 Boolean 타입으로 변환 후 참, 거짓 판단

- switch 
  
  - 조건 표현식의 결과값이 어느 값에 해당하는지 판별
  
  - 표현식의 결과값과 case문의 오른쪽 값을 비교
  
  - break, default 문은 선택적으로 사용 가능
  
  - break, default 문 까지 다음 조건문 실행
  
  ```js
  if(condition){
  }    else if (condition){
  }    else{
  }    
  
  
  ```

```js
const numone = 5
const numtwo = 10

if (operator ==='+') {
    console.log(numone + numtwo)
}   else if (operator ==='-') {
    console.log(numone - numtwo)
}   else if (operator ==='*') {
    console.log(numone * numtwo)
}   else if (operator ==='/') {
    console.log(numone / numtwo)
}   else {
    console.log('유효하지 않은 연산자입니다.')
}
```

## 반복문

- while
  
  - 조건문이 참인 동안 반복 시행
  
  - 조건은 소괄호 안에 작성
  
  - 실행할 코드는 중괄호 안에 작성
  
  - 블록 스코프 생성

```js
let i = 0
while(i < 6) {
    console.log(i)
    i +=1
}
```

- for
  
  - 세미콜론으로 구분되는 세 부분으로 구성
  
  - initialization
    
    - 최초 반복문 진입 시 1회만 실행되는 부분
  
  - condition
    
    - 매 반복 시행 전 평가되는 부분
  
  - expression
    
    - 매 반복 시행 이후 평가되는 부분
  
  - 블록 스코프 생성

```js
for (initialization; condition; expression){
    // do something
}
```

- for... in 
  
  - 객체의 속성을 순회할 때 사용, 객체 순회 적합
  
  ```js
  for ( variable in object) {
      // do something
  }
  ```

- for... of
  
  - 반복가능한 객체를 순회하며 값을 꺼낼 때 사용, 배열 순회 적합

```js
const fruits = ['딸기','바나나','메론']

for (let fruit of fruits){
    fruit = fruit + '!'
    console.log(fruit)
}
```



## 함수

- 함수 선언식, 함수 표현식으로 구분

- 변수에 할당 가능

- 함수의 매개변수로 전달 가능

- 함수의 반환 값으로 사용 가능

```js
function name(args) {
    //do something
}
```

```js
function add(num1,num2) {
    return num1 + num2
}
add(1,2)
```

## Arrow Function

- 함수를 비고젹 간결하게 정의할 수 있는 문법

- Function 키워드 생략 가능

- 함수의 매개변수가 단 하나 뿐이라면 () 도 생략 가능



## 문자열 주요 메서드

| 메서드      | 설명                         | 비고                 |
| -------- | -------------------------- | ------------------ |
| includes | 특정 문자열의 존재여부를 boolean으로 반환 |                    |
| split    | 문자열을 토큰 기준으로 나눈 배열 반환      | 없으면 기존 문자열을 반환     |
| replace  | 해당 문자열을 대상 문자열로 교체하여 반환    | replaceAll         |
| trim     | 문자열의 좌우 공백 제거하여 반환         | trimStart, trimEnd |

- string.includes(value)
  
  - 문자열에 value가 존재하는지 판별 후 참, 거짓 반환

- string.split(value)
  
  - value가 없을 경우 기존 문자열을 배열에 담아 반환
  
  - value가 빈 문자열일 경우, 각 문자로 나눈 배열을 반환
  
  - value가 기타 문자열일 경우, 해당 문자열로 나눈 배열을 반환
  
  - string.replace(from,to)
    
    - 문자열에 from값이 존재하는 경우 1개만 to 값으로 교체하여 반환
  
  - string.replaceAll(from,to)
    
    - 전부 교체 하여 반환

- sting.trim()
  
  - 문자열 시작과 끝의 모든 공백문자 제거한 문자열 반환

- string.trimstart()
  
  - 문자열 시작의 공백문자 제거

- string.trimend()
  
  - 문자열 끝의 공백문자 제거



## Arrays

- 키와 속성들을 담고 있는 참조 타입 객체

- 순서를 보장

- 대괄호를 이용해 생성, 0을 포함한 양의 정수 인덱스로 특정 값에 접근가능

- 배열의 길이는 array.length 형태로 접근



## 배열 관련 주요 메서드

| 메서드             | 설명                           | 비고      |
| --------------- | ---------------------------- | ------- |
| reverse         | 반대로 정렬                       |         |
| push & pop      | 배열의 가장 뒤에 요소를 추가,제거          |         |
| unshift & shift | 배열의 가장 앞의  요소를 추가,제거         |         |
| includes        | 배열에 특정 값이 존재하는지 판별 후 참/거짓 반환 |         |
| indexOf         | 배열에 특정 값이 존재하는지 판별 후 인덱스 반환  | 없으면 -1  |
| join            | 배열의 모든 요소를 구분자를 이용하여 연결      | 구분자X 쉼표 |

## Spread operator

- 사용 시 배열 내부에서 배열 전개 가능

```js
const array = [1, 2, 3]
const newArray = [0, ...array, 4]


const.log(newArray)     // [0,1,2,3,4]
```






