# 자바스크립트 기본문법
## 코드 구조
``` javascript
//구문은 세미콜론 기준으로 구분
alert('Hello'); alert('World'); 

//줄바꿈 시 세미콜론 자동 삽입
alert('Hello') 
alert('World')

//코드 블록 끝에는 세미콜론X
for(;;) {} 
```

## 엄격 모드
``` javascript
// 모던 자바스크립트에서 지원하는 기능 활성화
'use strict';
```

## 변수
``` javascript
let x = 5; //변수 정의
x = "John";
const y = 6; //상수 정의
```
### 자바스크립트의 기본 자료형

|자료형|설명|
|-----|-----|
|숫자형| 정수 및 부동소수점 숫자 <br> 특수 숫자 값(special numeric value): Infinity, -Infinity, NaN|
|BigInt| 2<sup>53</sup>-1보다 크거나 -(2<sup>53</sup>-1)보다 작은 값|
|문자형| 문자열 저장 (글자형 없음) <br> 큰 따옴표(""), 작은 따옴표(''), 역 따옴표(backtick, ``)사용 |
|불린형|논리값 true/false|
|null|‘비어있음’, '존재하지 않음’을 나타내는 독립 자료형|
|undefined|값이 할당되지 않은 상태를 나타내는 독립 자료형|
|객체형|데이터 컬렉션이나 복잡한 개체(entity)를 표현|
|심볼형|객체의 고유한 식별자(unique identifier)를 만들 때 사용|

### typeof 연산자
``` javascript
typeof "foo" // "string"
typeof Symbol("id") // "symbol"
typeof undefined // "undefined"

typeof null // "object", null은 객체가 아님(언어상 오류)
typeof Math // "object", 내장객체는 객체형
typeof alert // "function"
```

## 상호작용
|종류|설명|
|----|---|
|prompty(question, [default])|입력 필드(input field), 확인(OK) 및 취소(Cancel) 버튼이 있는 모달 창 <br> 취소 또는 ESC 입력 시 null 반환|
|confirm(question)|확인(OK) 및 취소(Cancel) 버튼이 있는 모달 창 <br> 확인 입력 시 true, 취소 입력 시 false 반환|
|alert(message)|확인(OK) 버튼이 있는 모달 창|

## 연산자
|종류|설명|
|----|---|
|산술 연산자| 사칙 연산자(*, +, -, /), 나머지 연산자(%), 거듭제곱 연산자(**) |
|할당 연산자| a = b 형태의 할당 연산자, a *= 2 형태의 복합 할당 연산자|
|비트 연산자|인수를 32비트 정수로 변환하여 이진 연산
|조건부 연산자|cond ? resultA : resultB
|논리 연산자| AND 연산자 (&&) OR 연산자 (\|\|) NOT 연산자(!)
|nullish 병합 연산자| 피연산자 중 실제 값이 정의된 피연산자 반환
|비교 연산자|다른 값끼리 비교할 때 피연산자의 자료형을 숫자형으로 바꾼 후 비교를 진행, 문자열은 사전순으로 비교 (<, >, <=, >=)
|기타 연산자| 쉼표 연산자(마지막 표현식의 평가 결과만 반환)

``` javascript
//nullish 병합 연산자 예시
let firstName = null;
let lastName = null;
let nickName = "바이올렛";
alert(firstName ?? lastName ?? nickName ?? "익명의 사용자"); // 바이올렛
```
## 반복문
``` javascript
// 조건동안 본문 실행
while (condition) {
  ...
}

// 본문 실행 후 조건확인
do {
  ...
} while (condition);

// 구성요소 생략 가능, 모두 생략 시 무한 반복
for(let i = 0; i < 10; i++) {
  ...
}
```
- 삼항 연산자에 break, continue 사용 불가
## switch문
``` javascript
switch(x) {
  case 'value1':  // if (x === 'value1')
    ...
    [break]

  case 'value2':  // if (x === 'value2')
    ...
    [break]

  default:
    ...
    [break]
}
```

## 함수
### 함수 선언문
  ``` javascript
  function name(parameter1, parameter2 = default, ... parameterN) {
  // 함수 본문
  }
  name(parameter1, parameter2, ... parameterN); //함수 호출
  ```
### 함수 표현식
  ``` javascript
  let name = function(parameter1, parameter2) {
  // 함수 본문
  };
  name(parameter1, parameter2); //함수 호출
  ```
### 화살표 함수
  ``` javascript
  // 화살표(=>) 우측엔 표현식이 있음
  let sum = (a, b) => a + b;

  // 중괄호{ ... } 사용 시 본문에 여러 줄의 코드 작성 가능. return문 필수.
  let sum = (a, b) => {
  // ...
  return a + b;
  }

  // 인수가 없는 경우
  let sayHi = () => alert("Hello");

  // 인수가 하나인 경우
  let double = n => n * 2;
  ```