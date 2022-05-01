---
title: "Javascript Cheat Sheet"
date: 2022-05-01T12:52:10+09:00
draft: true
author: "strawberry oolong tea"
description: "Utilities when I use javascript"
categories: [Cheat Sheet]
tags: [What I Learned, Javascript]
aliases: ["migrate-from-jekyl"]
toc: true
---

## Array

### Prototype Methods

### What about array at javascript

자바스크립트 데이터 타입에는 원시 타입과 객체 타입이 있다.

원시 타입 (primitive data type)

- boolean
- null
- undefined
- number
- string
- symbol (ES6에서 추가되었다.)

객체 타입 (object/reference type)

- object

자바스크립트의 배열은 배열의 기능을 하는 객체 타입의 자료구조를 말한다.

배열을 `typeof` 키워드로 타입을 검사하면 `'object'`로 나타나기 때문에 Array prototype의 메서드인 `isArray()`를 사용해야 한다.

```javascript
console.log(typeof ["🍓", "🍓🍓", "🍓🍓🍓"]); // 'object'
console.log(Array.isArray(["🍓", "🍓🍓", "🍓🍓🍓"])); // true
console.log(Array.isArray("🍓", "🍓🍓", "🍓🍓🍓")); // false
```

## Object

## Scope

모든 식별자(변수 이름, 함수 이름, 클래스 이름 등)는 자신이 선언된 위치에 의해 다른 코드가 식별자 자신을 참조할 수 있는 유효 범위가 결정된다. 즉, 식별자가 유효한 범위를 스코프라고 한다.

```javascript
const strawberry = "I like strawberry";

function print() {
  const strawberry = "I love strawberry";
  console.log(strawberry);
}

print(); // 'I love strawberry'
```

위와 같은 상황에서 자바스크립트 엔진은 이름이 같은 `strawberry` 중에서 어떤 걸 참조해야할지 결정해야 한다. 이를 **식별자 결정**이라 한다.

자바스크립트 엔진은 스코프를 통해 어떤 식별자를 참조할 지 결정한다. 즉, 스코프란 **식별자를 검색할 때 사용하는 규칙**이라고 할 수 있다.

자바스크립트 엔진은 코드를 실행할 때 코드의 문맥<sup>context</sup>을 고려한다.

스코프를 통해 같은 이름의 식별자를 사용할 수 있다. 스코프 내에서는 식별자가 유일해야 하지만 다른 스코프에서는 같은 식별자를 사용할 수 있다.

이와 관련해서 `var` 키워드로 선언된 변수는 같은 스코프 내에서 중복 선언이 허용된다. 이는 변수값이 재할당되는 의도치 않은 부작용(side effect)를 초래할 수 있다.

### Lexical
