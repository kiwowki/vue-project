# vue를 이용한 포트폴리오 사이트 만들기

Vue.js는 현대적인 웹 애플리케이션을 개발하기 위한 JavaScript 프레임워크 중 하나입니다. Evan You에 의해 개발되었고, 가볍고 유연한 특징으로 유명합니다. Vue는 사용자 인터페이스를 만들기 위한 프레임워크로, 주로 웹 페이지에서 동적이고 반응형인 UI를 구축하는 데 사용됩니다.

컴포넌트 기반 아키텍처: Vue.js는 애플리케이션을 작은 독립적인 부분으로 나누는 컴포넌트 기반 아키텍처를 채택합니다. 각 컴포넌트는 자체적인 상태와 로직을 가지며, 재사용 가능하게 설계되어 복잡한 애플리케이션을 단순화하고 유지보수를 용이하게 합니다.

양방향 데이터 바인딩: Vue.js의 핵심 기능 중 하나로, 모델과 뷰 간의 양방향 데이터 바인딩을 제공합니다. 이는 데이터의 변화를 실시간으로 반영하므로, 사용자 인터페이스가 항상 최신의 상태를 유지합니다.

가상 DOM (Virtual DOM): Vue.js는 성능 최적화를 위해 가상 DOM을 사용합니다. 실제 DOM 조작 대신 가상 DOM을 통해 변경 사항을 추적하고 필요한 부분만 업데이트하여 렌더링 성능을 향상시킵니다.

디렉티브: Vue.js는 템플릿 내에서 특별한 속성인 디렉티브를 사용하여 간단한 로직을 추가할 수 있습니다. 예를 들어, v-if 디렉티브는 조건에 따라 요소를 렌더링하거나 숨길 수 있도록 해줍니다.   
<details>
<summary>디렉티브 예시</summary>
   
`<li v-for="(nav, key) in headerNav" :key="key">`
   
`<a href="nav.url">{{ nav.title }}</a>`
   
`</li>`
</details>

상태 관리(Vuex): 복잡한 애플리케이션에서 상태 관리는 중요합니다. Vue.js는 Vuex라 불리는 상태 관리 라이브러리를 제공하여 애플리케이션의 상태를 중앙에서 효과적으로 관리할 수 있게 해줍니다.

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

gsap 설치 : `npm install gsap`  
sass 설치 : `npm install sass`  
lenis 설치 : `npm install @studio-freight/lenis`   

## 트러블 슈팅

<details>
<summary>Whitespace 에러</summary>
유닉스 시스템에서는 한 줄의 끝이 LF(Line Feed)로 이루어지는 반면,   
윈도우에서는 줄 하나가 CR(Carriage Return)과 LF, 즉 CRLF로 이루어지는데   
Git이 이 둘 중 어느 쪽으로 선택할지 혼란이 온 것이다.

##### LF란?

LF는 Line-Feed의 약자이다.
단어가 타자기에서 비롯되었듯이, 커서는 그 자리에 둔 상태에서 종이만 한 줄을 올리는 동작을 말한다.
Mac, Linux(Unix)에서 사용되는 줄바꿈 문자열(\n)이다.

##### CRLF란?

CRLF는 Carriage Return Line-Feed의 약자이다.
여기서 Carriage Return이란 문장이 끝에 다다르면 커서는 위아래 이동 없이 가장 앞으로 이동하는 동작을 말한다.
즉, CRLF는 커서를 다음 라인의 맨 앞으로 이동하는 동작이다.
Windows에서 사용되는 줄바꿈 문자열(\r\n)이다.

###### OS마다 사용되는 줄바꿈 문자열이 다르기 때문에 git에서 어떤 의미로 받아들여야 할지 몰라 에러 메시지가 나타난 것이다. 에러를 해결하지 않으면 줄바꿈 문자에 의해 커밋 내역이나 설정 파일들이 이상해질 수 있으니 통일시키는 것을 추천한다.

###### core.autocrlf 설정을 통해 해결할 수 있다. Git에 코드를 커밋할 때 LF와 CRLF를 서로 변환해주는 기능이다. 또한 시스템 전체에 적용할 것이라면 global 옵션을 추가해주고, 해당 프로젝트에만 적용한다면 제외하여 작성해주면 된다.

해결방법(Windows, DOS)  
`git config --global core.autocrlf true` // 시스템 전체에 적용
⠀  
`git config core.autocrlf true` // 해당 프로젝트에만 적용

</details>
