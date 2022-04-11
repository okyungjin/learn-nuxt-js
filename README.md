# Table of Contents
- [Table of Contents](#table-of-contents)
  - [Build Setup](#build-setup)
- [Nuxt 소개](#nuxt-소개)
  - [Nuxt란?](#nuxt란)
  - [SSR (Server Side Rendering)](#ssr-server-side-rendering)
  - [CSR (Client Side Rendering)](#csr-client-side-rendering)
  - [SSR vs CSR](#ssr-vs-csr)
    - [1) 렌더링 방식](#1-렌더링-방식)
    - [2) 결과물 비교](#2-결과물-비교)
  - [왜 SSR을 쓰는가?](#왜-ssr을-쓰는가)
    - [1) 빠른 페이지 렌더링](#1-빠른-페이지-렌더링)
    - [2) SEO (Search Engine Optimization)](#2-seo-search-engine-optimization)
    - [3) OG (Open Graph) Tag](#3-og-open-graph-tag)
  - [Nuxt의 장점과 특징](#nuxt의-장점과-특징)
    - [Nuxt의 장점](#nuxt의-장점)
    - [Nuxt의 특징](#nuxt의-특징)
- [Nuxt 프로젝트 시작하기](#nuxt-프로젝트-시작하기)
  - [Nuxt 프로젝트 생성](#nuxt-프로젝트-생성)
    - [npm](#npm)
    - [presets](#presets)
  - [Nuxt 프로젝트 폴더 구조](#nuxt-프로젝트-폴더-구조)
    - [.nuxt](#nuxt)
    - [assets](#assets)
    - [layout](#layout)
    - [middleware](#middleware)
    - [pages](#pages)
    - [plugins](#plugins)
    - [static](#static)
    - [store](#store)

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

# Nuxt 소개
## Nuxt란?
Nuxt는 서버 사이드 렌더링 프레임워크이다.

Nuxt는 Vue.js로 빠르게 웹을 제작할 수 있게 도와주는 프레임워크이다.
Vuex, Router, Axios 같은 라이브러리들을 미리 구성하여
- 싱글 페이지 애플리케이션 (SPA, Single Page Application)
- 서버 사이드 렌더링 (SSR, Server Side Rendering)
- 정적 웹 사이트 (Static Generated Website)

를 쉽게 제작할 수 있다.

## SSR (Server Side Rendering)
SSR은 **서버에서 페이지를 그려 클라이언트(브라우저)로 보낸 후 화면에 표시하는 기법**이다.

## CSR (Client Side Rendering)
CSR로 생성된 웹은 먼저 빈 html을 받고, js가 mount 되면서 DOM을 그려나가며 화면을 채우는 구조이다.

## SSR vs CSR
### 1) 렌더링 방식
**SSR**은 html의 내용을 서버에서 만들어서 던져주고, **CSR**은 빈 html을 던져주고 js가 화면을 그려나간다는 차이점이 있다.

<img width="800" alt="ssr-vs-csr" src="https://user-images.githubusercontent.com/31913666/162686808-de3d58d5-cb33-435f-856c-a7bfb63d1fef.png">

### 2) 결과물 비교
개발자 도구의 `Network > Docs` 탭에서 서버에서 받아온 html을 확인하면 SSR인지 CSR인지 구분할 수 있다.

SSR로 만들어진 **Nuxt.js** 공식 문서의 html 파일을 확인해보면 html 내부에 내용이 모두 담겨져 있는 것을 확인할 수 있다.

<img width="1200" alt="스크린샷 2022-04-11 오후 4 46 12" src="https://user-images.githubusercontent.com/31913666/162689441-b76e8abf-1349-4c61-8a04-5e7f923cf211.png">


반면 SPA로 만들어진 **Google Career**의 html을 보면 `<div id="app-root"></div>` 의 내부가 비어있는 것을 확인할 수 있다.

<img width="1200" alt="스크린샷 2022-04-11 오후 4 47 36" src="https://user-images.githubusercontent.com/31913666/162689820-1c7e5157-0493-4c94-bf61-a11dcfa9e352.png">


## 왜 SSR을 쓰는가?
SSR의 주된 목적은 다음과 같다.

### 1) 빠른 페이지 렌더링
렌더링 관련된 로직이 서버에 존재하며, 브라우저는 완성된 html을 얻기 때문에 SPA 보다 렌더링 속도가 빠르다.

### 2) SEO (Search Engine Optimization)
SPA는 빈 html을 받기 때문에 크롤러에 의한 정보 수집이 어렵다. SSR은 html에 이미 내용이 담겨있기 때문에 SEO가 가능하다.

### 3) OG (Open Graph) Tag
url을 카카오톡이나 슬랙을 통해 공유했을 때 페이지에 대한 정보를 보여주는 것을 OG Tag라고 하는데, SSR을 사용하면 페이지 별로 OG Tag를 설정할 수 있다. 
반면, SPA는 하나의 html 만을 가지고 있기 때문에 페이지가 상이해도 OG Tag는 하나만 보여줄 수 있다.

## Nuxt의 장점과 특징
### Nuxt의 장점
Nuxt로 개발했을 때의 장점은 다음과 같다.
- SEO (검색 엔진 최적화)
- 초기 프로젝트 설정 비용 감소 및 생산성 향상
- 페이지 로딩 속도 및 사용자 경험 향상
  - 코드 스플리팅이 기본으로 설정되어 있음

### Nuxt의 특징
- SSR (서버 사이드 렌더링)
- 규격화된 폴더 구조 (layout, store, middleware, plugins 등)
- pages 폴더 기반의 자동 라우팅 설정
- 코드 스플리팅
- 비동기 데이터 요청 속성
- ES6/ES6+ 변환
- 웹펙을 비롯한 기타 설정

# Nuxt 프로젝트 시작하기
## Nuxt 프로젝트 생성
### npm
`npm init nuxt-app learn-nuxt-js`

### presets

<img width="500" alt="스크린샷 2022-04-11 오후 5 09 38" src="https://user-images.githubusercontent.com/31913666/162693127-9e69f6f1-16a7-4d16-b878-33f4a0868249.png">


## Nuxt 프로젝트 폴더 구조
### .nuxt
`npm run dev` 실행 시 Nuxt의 내용들이 `.nuxt` 폴더에 담긴다.

### assets
정적 웹 리소스

### layout
페이지의 레이아웃을 담당하는 레이아웃 컴포넌트들이 담기는 폴더

### middleware
SSR을 진행할 때 서버에서 브라우저에 파일을 넘기기 전에 항상 실행시키는 함수를 middleware라고 한다.

### pages
파일 기반 라우팅이 일어나는 폴더

### plugins
Vue Plugins에 대한 폴더

### static
SEO에 필요한 파일을 담는 폴더

### store
Vue Store에 대한 폴더