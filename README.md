# Vue In Action

1. 정의와 구조파악
2. 개발 스타일 (Options API vs Composition API)
3. Lifecycle 이해
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

## 2. 개발 스타일

Options API, Composition API 두 가지 방식중 선호에 맞는 방식을 선택한다.

### Options API

`data`, `method`, `mounted`등 객체를 사용하여 컴포넌트 로직을 정의한다.

* data: 컴포넌트에 사용될 상태(State), 데이터를 관리한다.
* methods: 속성 값을 변경하고 업데이트하는 함수
* LifeCycle: 컴포넌트 생명주기 여러 단계에 호출한다.

### Composition

내장된 API 함수들을 사용하여 컴포넌트를 정의한다. `<script setup>`과 함께 사용한다.

* ref, reactive: 반응형 데이터를 선언한다.
* methods: 객체를 선언하는 방식이 아닌 함수를 직접 만들어서 사용한다.
* LifeCycle: 컴포넌트 생명주기 여러 단계에 호출한다.

## 3. 생명 주기(Lifecycle)

컴포넌트가 생성되고 소멸되는 단계를 의미한다.

1. created: 마운팅, 렌더링 되기전에 실행된다.
2. mounted: 렌더링, DOM 노드 생성이 완료된 이후 실행된다.
3. updated: 컴포넌트 데이터가 변경되어 DOM이 렌더링 된 후 실행된다.

**<참고 자료>**

* [생명 주기 훅](https://ko.vuejs.org/guide/essentials/lifecycle.html)

## 4. 핵심문법 1(User Interface)

**<참고 자료>**

* [클래스와 스타일 바인딩](https://ko.vuejs.org/guide/essentials/class-and-style.html)
* [조건부 렌더링](https://ko.vuejs.org/guide/essentials/conditional.html)
* [리스트 렌더링](https://ko.vuejs.org/guide/essentials/list.html)

### 선언적 렌더링

데이터바인딩의 기본은 선언적 렌더링이다. `{{ message }}` 문법을 사용한다. 이중 중괄호는 데이터를 일반 텍스트로 해석한다.
실제 `HTML`로 출력하기 위해서는 `v-html`을 사용한다.

### 조건부 렌더링

* `v-if`의 조건식이 `true`일 때만 렌더링 된다.
* `v-show`: 항상 렌더링 된다. `css` 속성만 변화한다.

### 리스트 렌더링

* `v-for`: 리스트 렌더링

## 5. 핵심문법 2(Data)

### 이벤트 핸들링

* 인라인 핸들러: 동작하는 코드를 `HTML Element`에 직접 할당한다.
* 메서드 핸들러: 메서드(함수)를 이벤트 핸들러에 할당한다.

**<참고 자료>**

* [이벤트 핸들링](https://ko.vuejs.org/guide/essentials/event-handling.html)

### 계산된 속성

* `Computed`: 공통적으로 사용되는 로직 혹은 복잡한 로직을 미리 처리해서 계산된 데이터 형태로 만든다. 캐싱(Caching)

**<참고 자료>**

* [계산된 속성](https://ko.vuejs.org/guide/essentials/computed.html)

* `Watch`: 데이터의 변경을 감시하고 있다가 값이 변경되었을 때 로직을 실행한다.
* `Props` & `Emits` / 데이터 주고받기
    * Props: 부모컴포넌트에서 선언된 데이터를 자식컴포넌트에서 사용 (상위 -> 하위)
    * Emits: 자식컴포넌트에서 부모컴포넌트로 데이터를 전달 (상위 <- 하위)
* `v-model`: 양방향 데이터 바인딩
