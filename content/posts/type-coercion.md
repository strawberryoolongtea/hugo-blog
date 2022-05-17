---
author: "strawberry oolong tea"
title: "Type Coercion"
date: 2022-05-16T18:29:28+09:00
draft: true
description: ""
categories: [Books]
tags: [What I Learned, Javascript, Javascript Deep Dive]
aliases: ["migrate-from-jekyl"]
toc: true
---

## Type Coercion

개발자의 의도에 따라 다른 타입으로 변환하는 것을 **명시적 타입 변환**<sup>explicit coercion</sup> 또는 **타입 캐스팅**<sup>type casting</sup>이라고 합니다.

반면 개발자의 의도와는 상관없이 표현식을 평가하는 도중에 자바스크립트 엔진에 의해 타입이 자동으로 변환되는 것을 **암묵적 타입 변환**<sup>implicit coercion</sup> 또는 **타입 강제 변환**<sup>type coercion</sup>이라고 합니다.

자바스크립트 엔진은 가급적이면 에러를 발생시키지 않도록 하기 위해 암묵적으로 타입을 변환해 표현식을 평가합니다.
