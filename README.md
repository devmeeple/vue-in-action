# Vue In Action

1. 정의와 구조파악
2. 개발스타일 (Options API vs Composition API)
3. LifeCycle 이해
4. 핵심문법 1(UserInterface)
    - 선언적 렌더링(텍스트보간법 & v-html)
    - Class와 Style 바인딩
    - 조건부렌더링 (v-if와 v-show)
    - 리스트렌더링 (v-for)
5. 핵심문법 2(Data)
    - 이벤트 핸들링
    - Computed
    - Watch
    - Props와 Emits
    - v-model
6. 컴포넌트(Component)
    - 정의와 활용방법
    - Slot을 활용한 컴포넌트 동적활용
7. 디자인패턴(Atomic Design Pattern)
8. 컴포지션 API(Composition API)
    - Setup 키워드란?
    - Options API와 비교하며 살펴보기
    - TypeScript와는 어떻게 접목시킬 수 있을까?

**<참고 자료>**

* [Vue.js](https://ko.vuejs.org/guide/introduction.html)
* [구디사는 개발자 9Diin '2024 Vue.js 개발 가이드 - Full Course (feat. Composition API)'](https://youtu.be/9lWaIhE05m8?si=3gp1eK_cgxDXjpeQ)

## 1. Vue.js

* 선언적 렌더링(Declarative Rendering): HTML 표준 문법을 확장해서 JavaScript 상태 기반으로 작성한다.
* 반응성(Reactivity): 상태 변경을 추적한다. 변경이 발생하면 DOM을 효율적으로 업데이트한다.
* SPA(Single-Page Application): 하나의 페이지에서 유저가 원하는 정보만 보여준다.
* SFC(Single-File Component): HTML, CSS, JavaScript를 `.vue` 파일 하나에서 관리한다.

**<참고 자료>**

* [소개](https://ko.vuejs.org/guide/introduction.html)
