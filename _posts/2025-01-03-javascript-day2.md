---
title: "[JS] JavaScript 공부 2일차"
date: 2025-01-03 12:00:00 +0900
categories: [Learn, JavaScript]
tags: [JavaScript]
---

> 자바스크립트 공부하기 2일차
>
> 산술 연산자, 비교 연산자, 논리 연산자

<hr />

## 산술 연산자

#### 종류

덧셈(+), 뺄셈(-), 곱셈(\*), 나눗셈(/), 나머지(%)

#### 예제1

```
let num1 = 1;
let num2 = 2;

console.log(num1 + num2);
console.log(num1 - num2);
console.log(num1 * num2);
console.log(num1 / num2);
console.log(num1 % num2);
```

출력결과

```
3
-1
2
0.5
1
```

#### 우선순위

곱셈, 나눗셈, 나머지 연산자는 덧셈, 뺄셈 연산자보다 우선순위가 높다.  
동등한 우선순위를 가질 때는 왼쪽에서 오른쪽으로 차례대로 계산한다.  
소괄호를 사용하면 원하는 연산부터 먼저 계산할 수 있다.

#### 예제2

```
let result1 = 1 + 2 * 10;
let result2 = (1 + 2) * 10;

console.log(result1);
console.log(result2);
```

출력결과

```
21
30
```

result1은 1 + (2 \* 10) 과 같으며 곱셈 먼저 연산 후 덧셈 연산이 진행되어 결과는 21이다.  
result2는 소괄호 내의 연산 후 곱셈 연산이 진행되어 결과는 30이다.

## 비교 연산자

두 값을 비교하는 연산자이다.

- === : 같다
- !== : 같지 않다
- \> : 크다
- \>= : 크거나 같다
- < : 작다
- <= : 작거나 같아

```
let num1 = 1;
let num2 = 2;

console.log(num1 === num2);
console.log(num1 !== num2);
console.log(num1 > num2);
console.log(num1 < num2);
```

출력결과

```
false
true
false
true
```

num1 === num2: 1과 2는 같다 => false  
num1 !== num2: 1과 2는 같지 않다 => true  
num1 > num2: 1은 2보다 크다 => false  
num1 < num2: 1은 2보다 작다 => true

## 논리 연산자

논리 연산자는 참과 거짓을 포함하는 불리언 값을 다룰 때 사용하는 연산자이다.

#### 종류

OR (||) : 둘 중 하나라도 참이면 참  
AND (&&) : 둘 중 하나라도 거짓이면 거짓  
NOT (!) : 참이면 거짓, 거짓이면 참

#### OR 예제

```
let name = "Tom";
let age = "23";

if (name === "Mike" || age > 19) {
    console.log("통과");
} else {
    console.log("돌아가");
}
```

출력결과

```
통과
```

name이 Mike 이거나 age가 19세보다 크면 통과를 출력하는 예제이다.  
출력결과는 통과이다.

#### AND 예제

```
let gender = "M"
let age = "23";

if (gender === "F" && age > 19) {
    console.log("통과");
} else {
    console.log("돌아가");
}
```

출력결과

```
돌아가
```

gender가 F 이면서 age가 19세보다 크면 통과를 출력하는 예제이다.  
조건에 맞지 않으므로 출력결과는 돌아가이다.

#### NOT 예제

```
let age = "23";
const isAdult = age > 19;

if (!isAdult) {
    console.log("돌아가");
} else {
    console.log("통과");
}
```

출력결과

```
통과
```

age가 19세보다 작으면 돌아가를 출력하는 예제이다.  
age가 23이므로 출력 결과는 통과이다.

2일차 공부 끝
