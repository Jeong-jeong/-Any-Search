[![Netlify Status](https://api.netlify.com/api/v1/badges/df74271c-aec4-4115-b52f-60786d71e39e/deploy-status)](https://app.netlify.com/sites/objective-jang-bed822/deploys)

<strong>Deploy: https://objective-jang-bed822.netlify.app</strong>

# 프로젝트 개요


## 💬 설명

- Vue3과 OMDb API를 활용한 영화검색 사이트입니다

## 👍 깨달은 점

- Vanila.js의 로직과 비교하여 Vue 프레임워크의 장점을 알 수 있었습니다.
    - created, mounted, updated, destroyed 등 컴포넌트 라이프 사이클이 확실히 구분되어 있어 로직이 들어가야 할 시점을 명확히 구분할 수 있었습니다.
    - v-if, v-model 등 디렉티브를 활용해 가시성 있고 효율적으로 코드를 작성할 수 있었습니다.
    - `props & $emit`, `provide & inject` , `vuex` 등 props drilling을 보완하기 위한 다양한 수단을 활용한다는 것을 깨달았습니다.
    - vuex의 store를 사용해 컴포넌트 전역에서 사용할 state와 actions를 관리할 수 있어서 편했습니다.
    - html, css, JS 를 template, style, script로 명확히 분리해 직관성을 높일 수 있었습니다.
- 배포 서비스로 Netlify라는 Faas의 사용법을 알고, 환경변수로 중요 정보를 숨기는 법을 배웠습니다.
- 인피니티 스크롤과 Interception Observer의 사용법을 알고 일반 scroll 이벤트와의 차이점을 배웠습니다.
- 모바일, 태블릿, 데스크탑을 고려한 반응형 페이지를 만들고 grid의 사용법을 익혔습니다.

## 🥶 아쉬웠던 점

- 프로젝트 규모가 작았음에도 props-drilling을 피하기 위해 provide & inject 등을 적극적으로 활용하지 않았습니다.
- SCSS의 mixin과 변수를 잘 활용해 재사용성을 높였으나, 컴포넌트화 시키지 않아 코드 길이가 길고 재사용성이 떨어집니다.
- computed와 methods 옵션을 명확히 구분하고 사용하지 못했습니다.
- 비동기 API를 axios와 fetch 둘다 사용하여 통일성 떨어진다 느꼈습니다.

## 🙆‍♀️ 다음 목표

- 페이지 단위가 아닌 컴포넌트 단위로 재사용성을 높이기
- computed와 methods 옵션을 명확히 구분하여 사용하기
- 비동기 API를 하나로 통일화하기
- 로딩뿐만 아니라 스켈레톤 UI도 적용해보기

---

## 🤸🏽‍♀️ Any-Search 회고록

[고뇌록 | 첫 Vue 프로젝트 : 영화 검색 사이트](https://velog.io/@jeongs/%EA%B3%A0%EB%87%8C%EB%A1%9D-%EC%B2%AB-Vue-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EC%98%81%ED%99%94-%EA%B2%80%EC%83%89-%EC%82%AC%EC%9D%B4%ED%8A%B8)


