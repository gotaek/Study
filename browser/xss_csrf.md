# XSS와 CSRF

# XSS

XSS는 크로스 사이트 스크립팅(Cross Site Scripting)으로 웹 사이트의 관리자가 아닌 권한이 없는 사람이 웹사이트에 악성 스크립트를 삽입하여 공격하는 기법을 말한다. 

## 공격 종류

### 1. Persistent XSS (저장 XSS)

공격자는 악성 스크립트를 서버에 삽입하여 영구적으로 데이터베이스에 저장되도록한다. 이때 웹사이트를 사용하는 사용자들은 해당 스크립트로 인해 공격을 받게 된다.

### 2. Reflected XSS (반사 XSS)

공격자는 악의적인 스크립트가 담긴 URL을 사용자가 누르도록 유도하고, 사용자가 URL을 누르면 악의적인 스크립트가 실행 되면서 공격 받게 된다. 스크립트 내용이 URL에 노출되기는 하지만 인코딩한다면 사용자가 제대로 파악할 수 없기 때문에 이런 방식에 공격 당할 수 있다. 

### 3. DOM based XSS (DOM 기반 XSS)

Reflected XSS와 마찬가지로 사용자가 악의적인 스크립트가 담긴 URL을 누르도록 유도한다. Reflected XSS와 차이점은 서버 측에서 탐지할 수 없다는 점이다. 클라이언트 측에서 악성 스크립트가 DOM 의 일부로 생성되기 때문이다. 

## 방지방법

XSS는 기본적으로 `<script>` 태그를 삽입하며 이루어지기 때문에 `<`, `>` 와 같은 문자를 `&lt;`, `&gt;`로 변경되게 하여 브라우저에서는 일반 문자로 인식되게 하는 방법을 사용할 수 있다. 또한 XSS방지 라이브러리, 브라우저 확장 기능을 사용함으로 방지할 수 있다. 웹 방화벽을 사용하는 것도 하나의 방법이 될 수 있다.

---

출처:

[https://noirstar.tistory.com/266](https://noirstar.tistory.com/266)

[https://github.com/baeharam/Must-Know-About-Frontend/blob/main/Notes/security/xss-csrf.md](https://github.com/baeharam/Must-Know-About-Frontend/blob/main/Notes/security/xss-csrf.md)

[https://tecoble.techcourse.co.kr/post/2021-04-26-cross-site-scripting/](https://tecoble.techcourse.co.kr/post/2021-04-26-cross-site-scripting/)
