# ES6

자바스크립트가 개발될 당시 마이크로소프트는 인터넷 익스플로러의 시장 점유율을 높이기 위해서 자신의 브라우저에서만 동작하는 기능들을 추가한 JScript를 적용했다. 이에 따라 자바스크립트 기능이 브라우저마다 제각각인 크로스 브라우징 이슈가 등장하였다. 모든 브라우저에서 정상적으로 웹페이지가 동일하게 동작하게 하기 위해서 자바스크립트의 표준화가 필요했다. 

컴퓨터 시스템의 표준을 관리하는 비영리 표준화 기구, ECMA인터내셔널에서 자바스크립트의 표준화가 성공적으로 이루어졌고, ECMAScript라는 이름으로 불리게 된다. 현재까지도 버전업이 계속 되고 있으며 우리에게 가장 유명한 버전은 ES6이다. ES5에서 제기된 문제들이 해결되었고, let/const 키워드, 화살표 함수, 클래스, 모듈 등과 같은 기능들이 대거 도입되었기 때문에 많이 거론된다.

**자바스크립트와 ECMAScript**

ECMAScript는 자바스크립트의 표준 사양인 ECMA-262를 말하는 것이다. 이는 핵심 문법을 규정하고 있으며 자바스크립트는 ECMAScript의 사양을 준수하는 범용 프로그래밍 언어를 말하는 것이다. 브라우저가 별도로 지원하는 클라이언트 사이드 Web API와 ECMAScript를 아우르는 것이 자바스크립트이다. 자바스크립트는 ECMAScript를 아우르는 개념이라고 보면 된다.

클라이언트 사이드 Web API는 브라우저가 지원하는 API로 DOM, Canvas, XMLHttpRequest, fetch, Web Storage등이 포함된다. 

**자바스크립트 엔진**

자바스크립트 엔진은 자바스크립트 인터프리터라고 부르며 브라우저마다 각각의 자바스크립트 엔진을 가지고 있다. 각 브라우저는 ECMAScript를 참조해 자바스크립트 엔진을 제작하지만 각 브라우저마다 지원되는 범위가 다르며 수행 능력 또한 차이가 난다. 구글 크롬에는 V8 자바스크립트 엔진을 사용하고 있는데 이는 다른 브라우저의 자바스크립트 엔진보다 속도가 빠르다. 

ES6에는 다음과 같은 기능들이 추가되었다.

- const, let
- 화살표 함수(Arrow Function)
- 템플릿 리터럴 (Template Literals)
- 반복문 (for in , for of)
- 기본 매개 변수 (Default parameters)
- 객체 정의 방법 (Define Object)
- 객체 복사 (Copy Object)
- 배열 및 객체 비구조화 (Array and object destructing)
- 가져오기 및 내보내기 (Import and export)
- 프로미스 (Promises)
- 나머지 매개 변수 및 확산 연산자 (Rest parameter and Spread operator)
- 클래스(Classes)

각각의 기능들에 대해서는 천천히 알아보도록 하자

[https://ssungkang.tistory.com/entry/ES6-ES는-무엇인가-왜-ES6인가](https://ssungkang.tistory.com/entry/ES6-ES%EB%8A%94-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80-%EC%99%9C-ES6%EC%9D%B8%EA%B0%80)

모던 자바스크립트 Deep Dive
