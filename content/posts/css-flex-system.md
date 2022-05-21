---
author: "strawberry oolong tea"
title: "CSS Flexbox"
date: 2022-05-04T15:24:40+09:00
draft: true
description: ""
categories: [Programming]
tags: [What I Learned, CSS]
aliases: ["migrate-from-jekyl"]
toc: true
---

본 글은 [css-tricks.com](https://css-tricks.com/)의 [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)의 내용을 번역하고 [w3schools.com](https://www.w3schools.com/)의 [CSS Flexbox](https://www.w3schools.com/css/css3_flexbox.asp)의 내용을 참고하여 덧붙였습니다.

## How to design layout for Website

CSS Flexbox 레이아웃 모듈 이전에는 4가지의 레이아웃 방법이 있었습니다.

- 웹 페이지의 섹션을 나누는 블록 모드
- 텍스트를 위한 인라인 모드
- 2차원 테이블 데이터를 위한 테이블 모드
- 요소의 명시적인 위치를 이용하는 포지션 모드

플렉스 박스 레이아웃 모듈은 `float` 속성을 이용하거나 포지셔닝하지 않고도 반응형의 유연한 레이아웃 구조를 디자인하기 쉽게 해줍니다.

## Background

CSS 플렉스 박스 레이아웃 모듈은 컨테이너 내의 아이템들을 정렬하고 분배하는 데에 보다 효율적인 방식을 제공합니다.

플렉스 레이아웃의 메인 아이디어는, 사용 가능한 영역을 최대한 효율적으로 채우기 위해 컨테이너에게 아이템의 너비 및 높이를 변경할 수 있는 기능을 제공한다는 것입니다. 플렉스 컨테이너는 사용 가능한 영역을 채우기 위해 아이템을 확장하거나 오버플로우를 방지하기 위해 아이템을 축소합니다.

가장 중요한 점은 수직 기반인 블록이나 수평 기반인 인라인과 달리 방향에 구애받지 않는다는 것입니다.

한편, 플렉스 레이아웃은 페이지 단위 내에서는 잘 작동할 수 있지만 규모가 크거나 복잡한 애플리케이션을 지원하기에는 유연성이 부족합니다. 때문에 대규모 레이아웃의 경우에는 [그리드](https://css-tricks.com/snippets/css/complete-guide-grid/)가 더 유용할 수 있습니다.

## Basics and terminology

CSS 플렉스 박스는 단일 속성이 아닌 하나의 전체적인 모듈이기 때문에, 모듈 내의 모든 속성을 비롯해 많은 것을 포함합니다. 속성들의 일부는 부모 요소인 `flex container`에 설정하거나 또 다른 일부는 자식 요소인 `flex items`에 속성을 부여합니다.
