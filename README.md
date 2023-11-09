# vue를 이용한 포트폴리오 사이트 만들기
Vue.js는 현대적인 웹 애플리케이션을 개발하기 위한 JavaScript 프레임워크 중 하나입니다. Evan You에 의해 개발되었고, 가볍고 유연한 특징으로 유명합니다. Vue는 사용자 인터페이스를 만들기 위한 프레임워크로, 주로 웹 페이지에서 동적이고 반응형인 UI를 구축하는 데 사용됩니다.

컴포넌트 기반 아키텍처: Vue.js는 애플리케이션을 작은 독립적인 부분으로 나누는 컴포넌트 기반 아키텍처를 채택합니다. 각 컴포넌트는 자체적인 상태와 로직을 가지며, 재사용 가능하게 설계되어 복잡한 애플리케이션을 단순화하고 유지보수를 용이하게 합니다.

양방향 데이터 바인딩: Vue.js의 핵심 기능 중 하나로, 모델과 뷰 간의 양방향 데이터 바인딩을 제공합니다. 이는 데이터의 변화를 실시간으로 반영하므로, 사용자 인터페이스가 항상 최신의 상태를 유지합니다.

가상 DOM (Virtual DOM): Vue.js는 성능 최적화를 위해 가상 DOM을 사용합니다. 실제 DOM 조작 대신 가상 DOM을 통해 변경 사항을 추적하고 필요한 부분만 업데이트하여 렌더링 성능을 향상시킵니다.

디렉티브: Vue.js는 템플릿 내에서 특별한 속성인 디렉티브를 사용하여 간단한 로직을 추가할 수 있습니다. 예를 들어, v-if 디렉티브는 조건에 따라 요소를 렌더링하거나 숨길 수 있도록 해줍니다.

상태 관리 (Vuex): 복잡한 애플리케이션에서 상태 관리는 중요합니다. Vue.js는 Vuex라 불리는 상태 관리 라이브러리를 제공하여 애플리케이션의 상태를 중앙에서 효과적으로 관리할 수 있게 해줍니다.

가볍고 유연한 구조: Vue.js는 가볍고 간결한 문법을 가지고 있으며, 다른 프레임워크나 라이브러리와 쉽게 통합될 수 있습니다. 또한, 점진적인 도입이 가능하도록 설계되어 있어 기존 프로젝트에 쉽게 도입할 수 있습니다. 이는 개발자에게 높은 유연성을 제공합니다.


## 셋팅
`npm init vue@latest`
√ Project name: ... vue-project
√ Add TypeScript? ... <span style="color: blue">No</span> / Yes
√ Add JSX Support? ... No / <span style="color: blue">Yes</span>
√ Add Vue Router for Single Page Application development? ... No / <span style="color: blue">Yes</span>
√ Add Pinia for state management? ... <span style="color: blue">No</span> / Yes
√ Add Vitest for Unit Testing? ... <span style="color: blue">No</span> / Yes
√ Add an End-to-End Testing Solution? » <span style="color: blue">No</span>
√ Add ESLint for code quality? ... No / <span style="color: blue">Yes</span>
√ Add Prettier for code formatting? ... No / <span style="color: blue">Yes</span>