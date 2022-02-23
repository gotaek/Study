# CORS

CORS는 (Cross-Origin Resource Sharing) 다른 출처에 대한 resource를 공유하는 것을 말한다. 즉 어떤 출처에서 다른 출처의 resource 접근 권한을 부여하는 것이다. 

## 출처(Origin)

CORS에서 알아야 하는 것 중 하나는 출처이다. 

URL은 여러가지 구성요소를 가지고 있다. 

예) http://example.com:80/business/mart/item?category=14&id=2965

- 스킴(Scheme): 프로토콜 이름
- 호스트(Host): 특정 서버
- 포트 번호(Port):컴퓨터에서 실행되고 있는 수많은 프로세스들의 주소 (HTTP:80, HTTPS:443)
- 경로(Path): 원하는 자원이 있는 위치
- 쿼리(Query): 서버에 요청할 때 원하는 것을 상세하게 표현하기 위해 사용

두 URL을 비교했을 때 스킴, 호스트, 포트번호가 동일해야 같은 출처라고 한다. 

## SOP(Same-Origin Policy)

만약 다른 출처의 자원 공유를 무작정 허용한다면 CSRF 나 XSS같은 방법으로 웹사이트가 공격받을 수 있다. 그래서 다른 출처의 자원을 사용하는 것을 막는 정책이 필요한데 이것이 SOP이다. 그러나 이러한 정책은 외부 API를 사용해야 하는 경우에 SOP는 큰 장애물이 된다. 그래서 CORS라는 정책을 사용함으로 이런 불편함을 해결한다.

## CORS

CORS는 교차 출처 리소스 공유이다. 

기본적으로 클라이언트에서 서버로 리소스 자원을 요청할 때 요청 헤더 `Origin` 값을 포함한다. 이후 서버가 요청에 대해 응답할 때 응답 헤더의 `Access-Control-Allow-Origin` 값이 `Origin`의 값과 비교하여 유효한 경우에만 리소스를 공유할 수 있게 하는 기술이다. 요청헤더의 `origin`은 요청을 보낸 출처를 나타내는 것이고, `Access-Control-Allow-Origin` 의 값인 출처에서만 요청을 보냈을 때 리소스를 사용하게 하는 것이다.

## CORS 동작 방식

### Preflight Request

요청을 보낼 때 총 2번의 요청을 보내 유저 데이터의 영향을 제거하여 안전성을 보장하는 방식이다. 사전 요청을 보낸 후 실제 요청을 보낸다. 사전 요청은 OPTIONS 메소드를 사용해 다른 출처의 리소스 요청이 가능한지 확인하는 요청이다. 만약 가능하다면 실제 요청을 보낸다. 

![https://ingg.dev/static/26be1d707cb15727951f38d12977426f/2bef9/preflight.png](https://ingg.dev/static/26be1d707cb15727951f38d12977426f/2bef9/preflight.png)

사전 요청은 다음과 같이 `origin` , `Access-Control-Request-Method`, `Access-Control-Request-Headers` 등이 포함되는데 다음을 의미한다.

Preflight Request

```jsx
origin:요청출처
Acces-Control-Request-Method: 실제 요청의 메소드
Access-Control-Request-Headers: 실제 요청의 추가헤더
```

Preflight Response

```jsx
Access-Control-Allow-Origin: 서버 측 허가 출처
Access-Control-Allow-Methods: 서버 측 허가 메소드
Access-Control-Allow-Headers: 서버 측 허가 헤더
Access-Control-Allow-Max-Age: 응답 캐시 기간
```

## Simple Request

단순 요청은 사전 요청 없이 바로 요청을 보내는 것이다. 사전 요청을 보내지 않기 때문에 Preflight Request보다는 단순하고 빠르지만 데이터가 영향을 받을 수 있다는 단점이 있다. 

다음 조건을 모두 만족해야 한다.

- 메서드는 *GET POST HEAD* 중 하나
- 헤더는 *Accept, Accept-Language, Content-Language, Content-Type* 만 허용
- Content-Type 헤더는 다음의 값들만 허용
    - application/x-www-form-urlencoded
    - multipart/form-data
    - text/plain

![https://ingg.dev/static/95cbd29b2b46519a7d1ec49aeb67bc90/efc66/simple2.png](https://ingg.dev/static/95cbd29b2b46519a7d1ec49aeb67bc90/efc66/simple2.png)

## Credentialed Request

이 방법은 다른 출처간 통신에서 보안을 강화하는 방법으로 credentials 옵션을 변경함으로 쿠키, 인증정보 등을 포함시킬 수 있다.

옵션은 세가지가 존재한다.

- ***omit*** : 절대로 cookie 들을 전송하거나 받지 않는다.
- ***same-origin*** : 동일 출처(same origin)이라면, user credentials (cookies, basic http auth 등..)을 전송한다. (default 값)
- ***include*** : cross-origin 호출이라 할지라도 언제나 user credentials (cookies, basic http auth 등..)을 전송한다.

## CORS 해결 방법

1. 백엔드: 서버측 응답에서 접근 권한을 주는 헤더(Access-Control-Allow-Origin)를 추가하여 해결
2. 프론트 엔드: 프록시 서버를 설정하여 해결

---

출처 및 참고

[https://evan-moon.github.io/2020/05/21/about-cors/#cors는-어떻게-동작하나요](https://evan-moon.github.io/2020/05/21/about-cors/#cors%EB%8A%94-%EC%96%B4%EB%96%BB%EA%B2%8C-%EB%8F%99%EC%9E%91%ED%95%98%EB%82%98%EC%9A%94)

[https://ingg.dev/cors/](https://ingg.dev/cors/)

[https://developer.mozilla.org/ko/docs/Web/HTTP/CORS](https://developer.mozilla.org/ko/docs/Web/HTTP/CORS)

[https://www.youtube.com/watch?v=-2TgkKYmJt4](https://www.youtube.com/watch?v=-2TgkKYmJt4)
