---
title: "Javascript And Browser"
date: 2022-05-01T12:52:10+09:00
draft: true
author: "strawberry oolong tea"
description: ""
categories: [Books]
tags: [What I Learned, Javascript, Javascript Deep Dive]
aliases: ["migrate-from-jekyl"]
toc: true
---

## Rendering Process Of Browser

브라우저는 다음과 같은 과정을 통해 렌더링[^1]을 수행합니다.

- 브라우저는 렌더링에 필요한 리소스(HTML, CSS, 자바스크립트)를 서버에 요청하고 응답을 받습니다.
- 브라우저의 렌더링 엔진은 응답받은 HTML과 CSS를 파싱[^2]하여 DOM과 CSSOM을 생성합니다.
- DOM과 CSSOM을 결합하여 렌더 트리를 생성합니다.
- 브라우저의 자바스크립트 엔진은 자바스크립트를 파싱하여 [AST](https://yceffort.kr/2021/05/ast-for-javascript)를 생성하고 바이트코드로 실행합니다.
- 이때 자바스크립트는 DOM API를 통해 DOM이나 CSSOM을 변경할 수 있습니다.
- 변경된 DOM과 CSSOM은 다시 렌더 트리로 결합됩니다.
- 생성된 렌더 트리를 기반으로 레이아웃을 계산하고 브라우저 화면에 HTML 요소를 페인팅합니다.

## Request & Response

서버에 리소스를 요청하기 위해 브라우저는 주소창을 제공합니다. 브라우저의 주소창에 URL을 입력하면 URL의 호스트 이름이 DNS를 통해 IP 주소로 변환되고 이 IP 주소를 갖는 서버에게 요청을 전송합니다.

### URI, URL, URN

URL<sup>Uniform Resource Locator</sup>은 서버가 제공되는 환경에 존재하는 파일의 위치를 말합니다.

<!-- `https://www.example.com` -->

[^1]: 렌더링은 HTML, CSS, 자바스크립트로 작성된 문서를 파싱하여 브라우저에 시각적으로 출력하는 것을 말합니다.
[^2]: 파싱은 프로그래밍 언어로 작성된 텍스트 문서를 해석하고 실행하기 위해 텍스트 문서의 문자열을 토큰으로 분해하고 토큰에 문법적 의미와 구조를 반영하여 트리 구조의 자료구조인 파스 트리를 생성하는 일련의 과정을 말합니다. 여기서 토큰은 문법적으로 더는 나눌 수 없는 코드의 기본 요소를 의미합니다. 일반적으로 파싱이 완료된 후에 파스 트리를 기반으로 중간 언어인 [바이트코드](https://ko.wikipedia.org/wiki/%EB%B0%94%EC%9D%B4%ED%8A%B8%EC%BD%94%EB%93%9C)를 생성하고 실행합니다.
