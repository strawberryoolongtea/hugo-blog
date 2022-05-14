---
author: "strawberry oolong tea"
title: "Control Flow Statement"
date: 2022-05-14T19:17:55+09:00
draft: true
description: ""
categories: [Books]
tags: [What I Learned, Javascript, Javascript Deep Dive]
aliases: ["migrate-from-jekyl"]
toc: true
---

## Control Flow Statement

제어문은 조건에 따라 코드 블록을 실행하거나 반복 실행하도록 하는 등 코드의 실행 흐름을 제어하는 것을 말합니다.

## Block Statement

블록문은 말그대로 코드로 이루어진 블록을 말합니다. 0개 이상의 문을 중괄호로 묶어 표현합니다. 자바스크립트는 블록문을 하나의 실행 단위로 취급합니다. 블록문은 일반적으로 단독으로 사용하기 보다는 제어문이나 함수를 정의할 때 사용합니다.

## Conditional Statement

조건문은 조건식의 평가 결과에 따라 코드 블록의 실행을 결정합니다. 조건식은 참인지 거짓인지 Boolean 값으로 평가될 수 있는 표현식을 사용합니다. 자바스크립트에서는 `if...else` 문 또는 `switch` 문을 사용합니다.

### Ternary Operator

대부분의 `if...else` 문은 삼항 조건 연산자로 바꿔 쓸 수 있습니다. 만약 조건에 따라 단순히 값을 결정하여 변수에 할당하는 경우에는 삼항 조건 연산자를 사용하는 것이 가독성이 더 좋습니다. 조건에 따라 실행해야 할 내용이 복잡하고 여러 줄의 문이 필요하다면 `if...else` 문을 사용하는 것이 가독성이 좋습니다.

### `if...else` or `switch`

논리적인 참, 거짓으로 실행할 코드 블록을 결정하는 경우 `if...else` 문을 사용합니다. 참, 거짓보다는 다양한 상황<sup>case</sup>에 따라 실행할 코드 블록을 결정하는 경우에는 `switch` 문을 사용합니다.

## Loop Statement

## Break

## Continue
