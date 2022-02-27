# XSS와 CSRF

# XSS

XSS는 크로스 사이트 스크립팅(Cross Site Scripting)으로 웹 사이트의 관리자가 아닌 권한이 없는 사람이 웹사이트에 악성 스크립트를 삽입하여 공격하는 기법을 말한다. 

## 공격 종류

### 1. Persistent XSS (저장 XSS)

공격자는 악성 스크립트를 포함한 게시글을 올려 서버에 저장시킨다. 이후 그 게시글에 접근하는 사용자들은 해당 스크립트로 인해 공격을 받게 된다.

### 2. Reflected XSS (반사 XSS)

공격자는 악의적인 스크립트가 담긴 URL을 사용자가 누르도록 유도하고, 사용자가 URL을 누르면 악의적인 스크립트가 실행 되면서 공격 받게 된다. 스크립트 내용이 URL에 노출되기는 하지만 인코딩한다면 사용자가 제대로 파악할 수 없기 때문에 이런 방식에 공격 당할 수 있다. 

### 3. DOM based XSS (DOM 기반 XSS)

Reflected XSS와 마찬가지로 사용자가 악의적인 스크립트가 담긴 URL을 누르도록 유도한다. Reflected XSS와 차이점은 서버 측에서 탐지할 수 없다는 점이다. 클라이언트 측에서 악성 스크립트가 DOM 의 일부로 생성되기 때문이다. 

## 방지방법

XSS는 기본적으로 `<script>` 태그를 삽입하며 이루어지기 때문에 `<`, `>` 와 같은 문자를 `&lt;`, `&gt;`로 변경되게 하여 브라우저에서는 일반 문자로 인식되게 하는 방법을 사용할 수 있다. 또한 XSS방지 라이브러리, 브라우저 확장 기능을 사용함으로 방지할 수 있다. 웹 방화벽을 사용하는 것도 하나의 방법이 될 수 있다.

---

# CSRF

XSS 가 사이트를 신뢰하는 것이라면 CSRF(Cross Site Request Forgery)는 웹사이트가 사용자를 신뢰하는 것이다. 사용자의 의지와는 무관하게 공격자가 웹사이트에 특정한 요청을 하는 기법을 CSRF라고 한다. 특정 이메일을 열어보거나 악성 웹사이트에 접속할 때 특정한 요청을 한다. XSS는 클라이언트 측에서 발생되는 것이라면 CSRF는 서버측에서 발생한다. 

## 방지방법

일반적으로 `referrer` 검증을 통해 대부분 방어가 가능할 수 있는데 이 방법은 요청 헤더의 `referrer`를 검증해 신뢰할 수 있는 도메인에서의 요청인지 확인한다. 두번째 방지방법은 토큰을 활용한 방법이다. 로그인을 하거나 어떤 작업 요청을 보낼 때 랜덤한 난수를 세션에 저장하고 사용자에게 보내 이후 요청부터 그 CSRF 토큰을 확인하면서 응답을 한다. 또 다른 방법은 우리가 흔히 볼 수 있는 CAPTCHA 방식이다. 간혹 어떤 웹사이트에 로그인을 할때 컴퓨터에서 보여지는 숫자 문자를 똑같이 쓰거나 ‘비행기가 포함된 이미지를 선택해주세요’라는 검사를 하는 경우가 있다. 이것이 CAPTCHA인데 인간과 로봇을 구분하기 위한 튜링테스트이다. 

---

출처:

[https://noirstar.tistory.com/266](https://noirstar.tistory.com/266)

[https://github.com/baeharam/Must-Know-About-Frontend/blob/main/Notes/security/xss-csrf.md](https://github.com/baeharam/Must-Know-About-Frontend/blob/main/Notes/security/xss-csrf.md)

[https://tecoble.techcourse.co.kr/post/2021-04-26-cross-site-scripting/](https://tecoble.techcourse.co.kr/post/2021-04-26-cross-site-scripting/)

[https://sj602.github.io/2018/07/14/what-is-CSRF/](https://sj602.github.io/2018/07/14/what-is-CSRF/)
