---
title: "[JS] JavaScript 공부 1일차"
date: 2025-01-02 20:00:00 +0900
categories: [Learn, JavaScript]
tags: [JavaScript]
---

> 자바스크립트 공부하기 1일차
> 변수와 상수, 자료형, 형 변환, 안내 메시지 표시 방법

<hr />

## 자바스크립트란?

예전에는 웹 페이지를 만들 때 사용하는 언어였는데, 요즘은 서버 개발 등도 할 수 있게 되었다.
웹 페이지의 요소는 HTML, CSS, 자바스크립트 3가지이고, 그중 자바스크립트는 웹 페이지 요소의 동작 정의를 할 때 사용한다.

## 변수와 상수

#### 변수

프로그램 실행 과정에서 변경될 수 있는 값을 저장하는 저장소

```
let age = 22; // age 변수를 선언하고 값으로 22 할당
console.log(age);

age = 23; // age 변수의 값을 23으로 변경
console.log(age);
```

출력결과

```
22
23
```

#### 상수

프로그램 실행 과정에서 변경되지 않는 값을 저장하는 저장소

```
const AGE = 23; // AGE 상수를 선언하고 값으로 23 할당
console.log(AGE);
```

출력결과

```
23
```

#### 변수명 선언 규칙

- 변수명은 문자, 숫자, $, \_ 를 조합하여 선언해야 한다.
- 변수명의 첫 글자는 숫자가 될 수 없다.
- 예약어는 변수명으로 사용할 수 없다. <a href="https://www.w3schools.com/js/js_reserved.asp" target="_blank">목록보기</a>
- 가급적 상수는 대문자로 선언한다.
- 변수명은 읽기 쉽고 이해할 수 있게 선언한다.

## 자료형

#### 문자형

문자열을 포함하는 자료형이다.  
문자형은 저장할 데이터를 큰따옴표나 작음따옴표로 감싸야 한다.  
또한 백틱(``)을 이용해도 문자형을 만들 수 있다.

```
let myName = "김동휘";
let myJob = 'developer';
console.log(`나는 ${myName}입니다. 나의 직업은 ${myJob}입니다.`);
```

출력결과

```
나는 김동휘입니다. 나의 직업은 developer입니다.
```

#### 숫자형

소수, 음수, 실수와 같은 모든 수의 종류를 포함하는 자료형이다.

```
let age = 23;
let tall = 175.4;
let minus = -20;
```

#### 불리언, null, undefined

불리언 형 (Boolean Type): 참과 거짓 (true, false) 를 저장하는 자료형이다.  
null: 변수에 아무런 값도 할당할 필요가 없을 때 사용한다.  
undefiend: 변수에 아무런 값도 할당되지 않으면 undefined 값을 가지게 된다.

```
let isEat = true; // 불리언 형 예시
let emptyVar = null; // null 예시
let realEmptyVar; // undefined 값 가짐
```

#### 자료 형 조회

typeof를 사용하면 변수의 자료형을 알 수 있다.

```
let age = 23; // 숫자형 변수 선언
console.log(typeof age); // 자료 형 조회
```

출력결과

```
number
```

## 형 변환

#### 묵시적 형 변환

자바스크립트 엔진이 스스로 알아서 변환하는 작업이다.

```
let number = 10;
let string = "20";
const RESULT = number + string; // 암묵적으로 숫자를 문자로 형 변환하여 계산
console.log(RESULT);
```

출력결과

```
1020
```

#### 명시적 형 변환

자바스크립트의 내장 함수 등을 이용해 의도적으로 자료형을 변경하는 작업
숫자형, 문자형, 불리언 형으로 변환 가능하다.

```
let strNum = "10";
let numYear = 2024;
let zero = 0;
let gap = "";

let realNum = Number(strNum); // 숫자형으로 변환
let strYear = String(numYear); // 문자형으로 변환

let boolStr = Boolean(strNum); // 문자열을 변환시 true 반환
let boolNum = Boolean(numYear); // 0이 아닌 숫자 변환시 true 반환
let boolZero = Boolean(zero); // 숫자 0은 false 반환
let boolGap = Boolean(gap); // 빈 문자열은 false 반환

console.log(realNum, strYear, boolStr, boolNum, boolZero, boolGap);
```

출력결과

```
10 '2024' true true false false
```

<br />
참고: 자바스크립트에서 불리언 형 변환은 truthy & falsy 규칙을 따른다.

## 안내 메시지 표시 방법

#### alert

알림을 보낼 때 사용

```
alert("삭제 처리하였습니다.");
```

<img src="/assets/img/posts/javascript-day1/ex-alert.png" alt="alert 예제" width="400">

#### prompt

값을 입력받을 때 사용, 취소하면 null이 저장됨

```
let age = prompt("당신의 나이는?");
```

<img src="/assets/img/posts/javascript-day1/ex-prompt.png" alt="prompt 예제" width="400">

#### confirm

확인받을 때 사용 (취소 또는 확인)

```
confirm("정말로 삭제하시겠습니까?");
```

<img src="/assets/img/posts/javascript-day1/ex-confirm.png" alt="confirm 예제" width="400">

1일차 공부 끝
