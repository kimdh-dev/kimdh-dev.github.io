---
title: "[JS] JavaScript 공부 5일차"
date: 2025-01-08 22:00:00 +0900
categories: [Learn, JavaScript]
tags: [JavaScript]
---

> 자바스크립트 공부하기 5일차
>
> 객체 (Object)

<hr />

## 객체

객체는 숫자형이나 문자형과 겉아 원시 자료형과 달리 다양한 값을 담는 자료형이다.

#### 객체의 생성

```
let person = {
    name: '김동휘',
    age: 23,
};
```

위의 person 객체는 2개의 프로퍼티로 구성되어있다.  
key는 name, value는 '김동휘'인 프로퍼티,  
key는 age, value는 23인 프로퍼티가 있다.

#### 객체 프로퍼티 접근

객체의 프로퍼티에 접근하려면 객체 이름 뒤에 점(.)을 찍고 프로퍼티 key를 명시해 해당 프로퍼티의 value에 접근하거나 (점 표기법)  
객체 이름 뒤에서 대괄호([])를 열고, 그 안에 원하는 프로퍼티의 key를 문자열로 명시하여 해당 프로퍼티의 value에 접근하는 방식이 있다. (괄호 표기법)

```
let person = {
    name: '김동휘',
    age: 23,
};
const personName = person.name;
const personAge = person['age'];
```

#### 프로퍼티 추가, 수정, 삭제

프로퍼티 추가

```
let person = {
    name: '김동휘',
    age: 23,
};
person.gender = 'male';
person['nickname'] = 'handsome';
```

프로퍼티 수정

```
let person = {
    name: '김동휘',
    age: 23,
};
person.name = '동휘';
person.age = '10';
```

프로퍼티 삭제

```
let person = {
    name: '김동휘',
    age: 23,
};
delete person.name;
delete person['age'];
```

#### 특정 프로퍼티가 존재하는지 여부 확인

특정 프로퍼티가 존재하는지 여부를 확인하려면 in 연산자를 사용한다.

```
let person = {
    name: '김동휘',
    age: 23,
};
let isNameExist = 'name' in person;
console.log(isNameExist);
```

출력결과

```
true
```

5일차 공부 끝
