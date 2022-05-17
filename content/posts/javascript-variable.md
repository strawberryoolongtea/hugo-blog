---
author: "strawberry oolong tea"
title: "Javascript Variable"
date: 2022-05-12T16:36:24+09:00
draft: true
description: ""
categories: [Books]
tags: [What I Learned, Javascript, Javascript Deep Dive]
aliases: ["migrate-from-jekyl"]
toc: true
---

## Why do we needs variables

데이터를 사용하기 위해서는 먼저 데이터를 기억해야 할 것입니다. 컴퓨터는 메모리에 데이터를 저장합니다. 메모리는 메모리 셀의 집합체를 말하며 각 메모리 셀은 고유한 주소를 가집니다. 메모리 주소는 데이터를 저장한 공간의 위치를 나타내게 됩니다. 저장된 데이터를 다시 사용하고자 할 때 메모리 주소로 직접 접근하게 되면 치명적인 오류가 발생할 수 있기 때문에 개발자의 직접적인 메모리 제어는 허용되지 않습니다. 이때 변수를 활용해 메모리 주소에 접근할 수 있습니다. 변수는 **데이터를 저장하기 위해 확보한 메모리 공간 자체 또는 그 공간을 식별하기 위한 이름**을 말합니다.

[메모리 관련 글](https://st-lab.tistory.com/198)

## Identifier

어떤 값을 구별해서 식별할 수 있는 고유한 이름을 식별자라고 하며 변수 또한 식별자입니다. **식별자는 값이 아닌 메모리 주소를 기억하고 있습니다.** 식별자를 통해 메모리 주소에 접근하고 이 메모리 주소에 저장된 데이터를 사용할 수 있게 됩니다. 식별자는 어떤 걸 가리키는 지 명확할수록 좋습니다. 때문에 변수, 함수, 클래스 등의 식별자 이름을 정할 때에는 사람(개발자)이 한번에 이해하기 쉽도록 이름 짓는 것이 중요합니다.

## Declaration

변수를 사용하기 위해서는 선언을 통해 변수를 생성해야 합니다. `var`, `let`, `const`와 같은 키워드로 변수를 선언하면 자바스크립트 엔진이 변수의 존재를 확인하고 값을 저장하기 위한 메모리 공간을 확보하고 변수 이름과 메모리 주소를 연결해 값을 저장하기 위한 준비를 하게 됩니다.

### var

`var` 키워드는 함수 레벨 스코프를 가집니다. 변수를 선언함과 동시에 `undefined`를 할당해 초기화합니다.

자바스크립트 엔진은 변수 선언을 다음과 같은 2단계에 거쳐 수행합니다.

- 선언 단계: 변수 이름을 등록해서 자바스크립트 엔진에 변수의 존재를 알립니다.
- 초기화 단계: 값을 저장하기 위해 메모리 공간을 확보하고 암묵적으로 undefined를 할당해 초기화합니다.

**`var` 키워드를 사용한 변수 선언은 선언 단계와 초기화 단계를 동시에 진행하게 됩니다.**

초기화<sup>Initialization</sup>란 변수가 선언되고 최초의 값을 할당하는 것을 말합니다. 메모리 공간은 임의로 사용되기 때문에 초기화를 거치지 않으면 이전에 사용한 쓰레기 값<sup>garbage value</sup>이 들어있을 수 있습니다. 때문에 undefined로 암묵적으로 초기화를 진행하면 garbage value를 사용할 위험으로부터 안전합니다.

선언하지 않은 식별자에 접근하면 [**ReferenceError**](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError)가 발생합니다.

## Hoisting

자바스크립트에서 변수 선언은 런타임 이전에 먼저 실행됩니다. 자바스크립트는 소스코드의 평가 과정을 거치면서 소스코드를 실행하기 위한 준비를 합니다. 이때 변수 선언을 포함한 모든 선언문(변수 선언문, 함수 선언문 등)을 소스코드에서 찾아내 먼저 실행합니다. 그리고 소스코드의 평가 과정이 끝나면 변수 선언을 포함한 모든 선언문을 제외하고 소스코드를 순차적으로 실행합니다. 이런 현상이 변수 선언문이 마치 선두로 끌어 올려진 것처럼 동작하기 때문에 변수 호이스팅<sup>variable hoisting</sup>이라고 합니다. 자바스크립트에서는 `var`, `let`, `const`, `function`, `class` 키워드를 사용해 선언하는 모든 식별자가 호이스팅됩니다. 모든 선언문이 런타임 이전 단계에 먼저 실행되기 때문입니다.

## Assignment

변수에 값을 할당할 때에는 할당 연산자 `=` 기호를 사용합니다. 할당 연산자는 우변의 값을 좌변의 변수에 할당합니다.

```javascript
var score; // 변수 선언
score = 80; // 값의 할당
```

변수 선언과 할당의 각 2개 문은 하나의 문으로 단축 표현할 수 있습니다.

```javascript
var score = 80; // 변수 선언과 값의 할당
```

변수 선언은 런타임 이전에 먼저 실행되지만 값의 할당은 런타임 시점에 실행됩니다.

다음 두 코드는 동일하게 동작합니다.

```javascript
console.log(score); // undefined

var score; // 변수 선언
score = 80; // 값의 할당

console.log(score); // 80
```

```javascript
console.log(score); // undefined

var score = 80; // 변수 선언과 값의 할당

console.log(score); // 80
```

변수의 선언과 값의 할당을 하나의 문장으로 단축 표현해도 자바스크립트 엔진은 이를 나누어 실행합니다.

## Allocation

`var` 키워드로 선언된 변수는 `undefined`로 초기화되어 있습니다. 이에 값을 할당하는 것 또한 재할당이라고 할 수 있습니다. 이와 같이 이전에 값을 버리고 새로운 값을 저장하는 것을 말합니다. 하지만 이는 같은 메모리 공간에서 값을 지우고 새로운 값을 저장하는 것이 아니라, 새로운 메모리 공간을 확보하고 그 메모리 공간에 재할당 값을 저장합니다.

```javascript
var score; // 변수 선언: 메모리 공간 A에 undefined를 초기화 및 저장합니다.
score = 80; // 값의 할당: 메모리 공간 B에 80을 저장합니다.
score = 90; // 값의 재할당: 메모리 공간 C에 90을 저장합니다.

// 메모리 공간 A와 B에 저장된 undefined와 80은 더 이상 필요하지 않습니다.
```

어떤 식별자와도 연결되어 있지 않은 값은 불필요한 값이며 이는 가비지 콜렉터<sup>garbage collector</sup>에 의해 메모리에서 자동 해제됩니다. 단, 메모리에서 언제 해제될지는 예측할 수 없습니다.

## Naming Conventions

식별자는 어떤 값을 구별할 수 있는 고유한 이름이어야 하며 이는 특정한 네이밍 규칙에 따라 적절하게 정해야 합니다.

- 식별자는 특수문자를 제외한 문자, 숫자, 언더스코어(`_`), 달러 기호 (`$`)를 포함할 수 있습니다.
- 식별자는 숫자로 시작하는 것은 허용하지 않습니다.
- [예약어](https://www.w3schools.com/js/js_reserved.asp)는 식별자로 사용할 수 없습니다.

```javascript
var strawberry-oolong-tea; // 언더스코어와 달러 기호를 제외한 특수문자는 사용할 수 없습니다.
var 0010ng; // 숫자로 시작할 수 없습니다.
var this; // 예약어는 사용할 수 없습니다.
```

ES5부터 식별자를 만들 때 유니코드 문자를 허용해 알파벳 외의 한글이나 일본어 식별자도 사용할 수 있습니다.

```javascript
var 딸기우롱차, いちごウーロン茶;
```

네이밍 컨벤션<sup>naming convention</sup>은 하나 이상의 영어 단어로 구성된 식별자를 만들 때 가독성 좋게 단어를 구분하기 위해 규정한 명명 규칙을 말합니다. 일반적으로 다음의 4가지 유형이 자주 사용됩니다.

```javascript
// camelCase 카멜 케이스
var strawberryOolongTea;

// snake_case 스네이크 케이스
var strawberry_oolong_tea;

// PascalCase 파스칼 케이스
var StrawberryOolongTea;

// typeHungarianCase 헝가리안 케이스
var strStrawberryOolongTea; // type + identifier
```
