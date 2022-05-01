---
author: "strawberry oolong tea"
title: "Hugo Post Guide"
date: 2022-04-30T23:14:55+09:00
description: "How to create hugo blog"
draft: true
categories: [Guide]
tags: [Today I Learned, SSG]
aliases: ["migrate-from-jekyl"]
toc: true
---

## Create Hugo Blog

휴고 블로그를 만드는 방법을 안내합니다.
휴고 프로젝트를 생성하는 방법부터 콘텐츠는 어떻게 추가하는지 커스터마이징은 어떻게 하는지 이야기합니다.

자세한 사항은 [Hugo Quick Start](https://gohugo.io/getting-started/quick-start/) 및 [Hugo Documentation](https://gohugo.io/documentation/)를 확인하세요.

아래부터 이어지는 방법론은 Mac 환경 및 [Tokiwa](https://github.com/heyeshuang/hugo-theme-tokiwa) 테마가 적용된 블로그를 기준으로 작성되었습니다. 윈도우 환경이나 다른 테마의 사용 방법과는 일부 차이가 있을 수 있습니다.

### Install Hugo

```
brew install hugo
```

### Create New Project

새로운 휴고 프로젝트를 생성합니다. 여기서는 `test-blog` 라는 프로젝트를 만들겠습니다.

```
hugo new site {project name}
```

```shell
hugo new site test-blog
```

다음과 같은 구조의 폴더가 생성됩니다.

```
.
├── archetypes
│   └── default.md
├── config.toml
├── content
├── data
├── layouts
├── public
├── static
└── themes
```

새롭게 생성한 프로젝트의 루트에서 깃을 초기화하고 원하는 테마의 서브모듈을 추가합니다.

```
cd {project name}
git init
git submodule add {git repository} {path}
```

휴고 블로그 테마는 [여기](https://themes.gohugo.io/)에서 확인할 수 있습니다.

```bash
cd test-blog
git init
git submodule add https://github.com/heyeshuang/hugo-theme-tokiwa.git themes/hugo-theme-tokiwa
```

**submodule**을 추가하고 나면 `.gitmodules` 파일이 다음과 같이 추가된 것을 확인할 수 있습니다.

```
[submodule "themes/hugo-theme-tokiwa"]
	path = themes/hugo-theme-tokiwa
	url = https://github.com/heyeshuang/hugo-theme-tokiwa.git
```

`config.toml` 파일을 다음과 같이 작성합니다.

```
baseURL = 'http://example.org/'
languageCode = 'en-us'
title = 'My New Hugo Site'
```

루트에서

```
hugo new posts/javascript-cheat-sheet.md
```

```shell
# default
---
title: "Javascript Cheat Sheet"
date: 2022-05-01T12:52:10+09:00
draft: true
---

# front matter
---
title: "Post Guide"
date: 2022-04-30T23:14:55+09:00
draft: true
author: "strawberry oolong tea"
description: "How to create hugo blog"
categories: [TIL]
tags: [guide, helloworld]
aliases: ["migrate-from-jekyl"]
toc: true
---
```

# This is heading1

## This is heading2

### This is heading3

This is paragraph

자바스크립트

> 타입스크립트

```

console.log("Hello world");

```

**hello**

`hello`

<mark>hello</mark>

<mark>salamanders</mark>

```

```
