---
title: "[JS] JavaScript 공부 6일차"
date: 2025-01-09 22:00:00 +0900
categories: [Learn, JavaScript]
tags: [JavaScript]
---

> 자바스크립트 공부하기 6일차
>
> 객체 method, this

<hr />

## 객체 method

객체에서 값이 method인 함수 프로퍼티를 'method'라고 한다.

```
let person = {
    name: '김동휘',
    age: 23,
    sayHi: function() {
        console.log('hi');
    }
};
person.sayHi();
```

## method에서 this의 사용

method에서 사용된 this는 해당 method를 호출한 객체로 바인딩된다.

```
let person = {
    name: '김동휘',
    age: 23,
    introduce: function () {
        console.log(`나의 이름: ${this.name}, 나의 나이: ${this.age}`);
    },
};
person.introduce();
```

출력결과

```
나의 이름: 김동휘, 나의 나이: 23
```

6일차 공부 끝
