# 미디어쿼리


media query는디바이스 타입이나 뷰포트의 너비 등에 의해 웹 사이트나 앱 스타일을 수정할 때 사용한다. 따라서 media query는 반응형 웹페이지를 제작하는데 큰 도움이 된다.

media query를 사용하기 위해서는 `@media`로 시작하고 뒤에는 다룰 디바이스의 타입을 지정한다. `print`, `screen`, `speech` 등의 기기를 설정할 수 있는데 아무것도 지정하지 않으면 default로 `all`이 지정되는데 모든 장치에 적용하는 것이다. 

media query에도 논리 연산자가 존재한다. `and`, `not` , `only`와 같은 논리 연산자를 사용해서 복잡한 쿼리를 만들 수 있다. `and` 는 미디어 특성이 모두 참일 때만 적용하는 것이고, `not`은 쿼리가 거짓일 때만 지정한 속성들이 나타나게 한다. `only`는 구형 브라우저의 오작동을 방지하기 위해서 주로 쓰이는 논리 연산자이다. 전체 쿼리가 참일때만 적용하게 하는 것으로 `only`를 사용할 때는 디바이스의 타입은 무조건 지정해야 한다. `,`를 사용할 수도 있는데 이는 or과 같은 역할을 한다.

논리 연산자를 작성했다면 그 다음 괄호 안에 `max-width`나 `min-width`를 설정해주면 된다. 이 외에도 `height`, `color` 등 많은 미디어 특성을 지정할 수 있는데 가장 많이 사용되는 것은 `max-width`, `min-width`, `orientation`(뷰포트의 방향)이다. `orientation:landscape`는 가로 방향을 의미하는 것이고 `orientation:portrait`은 세로 방향을 의미하는 것이다.

만약 다음과 같이 코드를 작성한다면 

```css
@media all and (max-width:500px){
	body{
		color:blue;
	}
}
```

화면의 너비가 500px이하일 때 `body`태그의 폰트 컬러는 파랑색으로 유지가 된다. 

브레이크 포인트는 다음과 같이 설정할 수 있다.

```css
/* 세로모드 모바일 디바이스 (가로 해상도가 576px 보다 작은 화면에 적용) */
@media (max-width: 575px) {...} 
 
/* 가로모드 모바일 디바이스 (가로 해상도가 576px보다 크고 768px 보다 작은 화면에 적용)  */
@media (min-width: 576px) and (max-width: 767px) {...}
 
/*태블릿 디바이스 (가로 해상도가 768px보다 크고 991px 보다 작은 화면에 적용)  */
@media (min-width: 768px) and (max-width: 991px) {...} 
 
/* 데스크탑 (가로 해상도가 992px보다 크고 1199px 보다 작은 화면에 적용)  */
@media (min-width: 992px) and (max-width: 1199px) {...} 
 
/* 큰화면 데스크탑 (가로 해상도가 1200px 보다 큰 화면에 적용)  */
@media (min-width: 1200px) {...}
```

모바일 웹 제작시 미디어 쿼리 에러가 나지 않게 하려면 아래와 같은 코드를 head태그 안에 넣는다. 

```html
<meta name="viewport" content="width=device-width, maximum-scale=1.0, minimum-scale=1, user-scalable=yes,initial-scale=1.0" />
```

출처

[https://log.designichthus.com/11](https://log.designichthus.com/11)

[https://developer.mozilla.org/ko/docs/Web/CSS/Media_Queries/Using_media_queries](https://developer.mozilla.org/ko/docs/Web/CSS/Media_Queries/Using_media_queries)
