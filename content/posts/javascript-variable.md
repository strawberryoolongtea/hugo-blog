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

데이터를 사용하기 위해서는 먼저 데이터를 기억해야 할 것입니다. 컴퓨터는 메모리에 데이터를 저장합니다. 메모리는 메모리 셀의 집합체를 말하며 각 메모리 셀은 고유한 주소를 가집니다. 메모리 주소는 데이터를 저장한 공간의 위치를 나타내게 됩니다. 저장된 데이터를 다시 사용하고자 할 때 메모리 주소로 직접 접근하게 되면 치명적인 오류[^1]가 발생할 수 있기 때문에 개발자의 직접적인 메모리 제어는 허용되지 않습니다. 이때 변수를 활용해 메모리 주소에 접근할 수 있습니다. 변수는 **데이터를 저장하기 위해 확보한 메모리 공간 자체 또는 그 공간을 식별하기 위한 이름**을 말합니다.

[^1]: 어떤 치명적인 결과가 생기는 걸까...

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

## Assignment

## Allocation

## Naming Conventions
