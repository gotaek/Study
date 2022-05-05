# SASS

# CSS 전처리기

CSS전처리기는 자신만의 특별한 문법을 가지고 있으며 CSS로 컴파일해주는 프로그램이다. 컴파일이란 전처리기로 작성한 코드가 웹에서도 동작할 수 있도록 표준 CSS로 바꿔주는 것이다. 그래서 전처리기를 이용하기 위해서는 컴파일러가 필요하다. 컴파일하는 과정이 추가되었기 때문에 표준 CSS를 사용하는 것보다 복잡하다. 그럼에도 CSS전처리기를 사용하는 이유는 유지보수성 때문이다. 중첩 선택자를 사용하기 쉬우며 반복되는 코드를 변수나 mixins를 통해 줄일 수 있기 때문에 재사용성을 높일 수 있다. 또한 CSS전처리기는 프로그래밍 언어와 비슷한 면이 있어서 조건문, 반복문 등을 사용할 수 있어 계산 및 논리에도 편리하다. 전처리기의 종류에는 Less, Sass, Stylus 등이 있다. Less는 진입 장벽이 낮기 때문에 Sass 다음으로 많이 사용된다. 가장 많이 사용되지 않는 이유는 기능의 한계가 존재하기 때문이다. Stylus는 깔끔하고 세련되었지만 버그가 많이 존재하기 때문에 많이 사용되지 않는다. Less와 Stylus의 장점 모두를 가지고 있는 것이 Sass이다. 

# SCSS와 SASS의 차이

SCSS는 Sass의 버전 3에서 등장한 문법으로 세미콜론과 중괄호가 추가되었다는 것이 눈에 띈다. 이것들이 추가되며 쉽게 구조를 파악할 수 있기 때문에 SCSS를 가장 많이 사용하는 것 같다. 이 외에도 mixins를 사용할 때 @mixin, @include를 사용한다.

```sass
.list
  width: 100px
  float: left
  li
    color: red
    background: url("./image.jpg")
    &:last-child
      margin-right: -10px
```

```scss
.list {
  width: 100px;
  float: left;
  li {
    color: red;
    background: url("./image.jpg");
    &:last-child {
      margin-right: -10px;
    }
  }
}
```

# 문법

## Nesting

표준 CSS에서는 자식 요소에 대해 접근할 때 부모 요소와 자식 요소를 공백으로 이어 선택한다. 다음처럼 말이다.

```css
div{
	padding:20px;
}
div span{
	color:red;
}
```

그러나 SCSS에서는 중첩을 허용하기 때문에 귀찮게 위와 같이 작성할 필요가 없어진다. 아래와 같이 어떤 태그의 자식 요소라면 중괄호 안에 그 요소를 넣어서 지정할 수 있으므로 보기에도 이해가 잘 되고 사용하기에도 더 편리하다.

```scss
div{
	padding:20px;
	span{
		color:red;
	}
}
```

만약 `div`에 `hover`이벤트 트리거를 주고 싶다면 어떻게 해야할까? `&` 키워드를 사용해 부모 선택자로 치환할 수 있다.

```scss
div {
  padding: 20px;

  span {
    color: red;
  }

  &:hover{
    background:teal;
  }
}
```

만약 `font-`, `margin-`, `background-`처럼 동일한 네임 스페이스를 가지는 속성들은 아래와 같이 사용할 수 있다.

```scss
div {
  margin: {
    top:20px;
    bottom:30px;
  }
  font: {
    size:16px;
    weight:bold;
  }
}
```

위의 코드는 아래처럼 컴파일 된다.

```css
div {
  margin-top: 20px;
  margin-bottom: 30px;
  font-size: 16px;
  font-weight: bold;
}
```

## Variable

색상이나 이미지같이 반복적으로 사용해야 하는 값을 변수로 지정하면 코드의 중복을 줄일 수 있다. Scss에서는 변수 이름 앞에는 `$`를 붙인다. 변수는 선언된 블록 내에서만 유효범위를 가진다. 그러나 변수 지정후 `!global` 플래그를 사용하면 전역으로 변수의 범위를 설정할 수 있다. 

```scss
.box1 {
  $color: yellow !global;
  background: $color;
}

.box2 {
  background: $color;
}
```

```css
.box1 {
  background: yellow;
}

.box2 {
  background: yellow;
}
```

`#{}`를 이용해서 코드의 어디에서든지 변수 값을 넣을 수 있다.

```scss
$family:unquote("Droid+Sans");
@import url("http://fonts.googleapis.com/css?family=#{$family}");
```

```css
@import url("http://fonts.googleapis.com/css?family=Droid+Sans");
```

Sass 내장 함수 `unquote()`는 문자의 따옴표를 제거한다고 한다. 

## @import

파일을 import할 때는 `@import`를 사용한다. 만약 여러 파일을 가져올 경우에는 `,`로 구분한다.

scss폴더에  variables.scss파일을 생성하고 다음과 같은 코드를 작성했다고 하자. 그러면 다른 파일에서 `@import "_variables";` 로 파일을 가져올 수 있다. 만약 scss파일이 여러개 존재하고 하나의 scss파일에서 import했다면 이를 css파일로 컴파일할 때 각각 컴파일되어 scss파일의 개수만큼 css파일이 생기게 되는데 만약 scss파일명의 가장 앞에 `_`를 사용하면 별도의 파일로 컴파일되지 않고 하나로 합쳐지게 된다. 이때 주의해야 할 점은 다른 파일들을 import하는 메인 파일에는 `_`를 붙이지 사용하지 않아야 한다는 것이다. 

```scss
/*변수 설정*/
$primary-color: yellow; 
$sub-color:green;
```

```scss
@import "_variables";

h2{
	color:$primary-color;
}
/* nesting */
.box{
	&:hover{
		background:$sub-color;
	}
	margin-top:20px;
	h2{
		color:$primary-color;
	}
	button{
		color:$primary-color;
	}
}

```

## Operations

Sass는 기본적인 연산 기능을 지원한다. `+`, `-`, `*`, `/`, `%` 산술 연산자를 사용할 수 있이며 `==`, `≠`, `<`, `>`, `≤`, `≥` 비교 연산도 가능하다. 또한 `and`, `or`, `not`과 같은 논리 연산자도 사용이 가능하다. 절대적 단위 연산할 때는 `25px - 10px` 처럼 그냥 사용하면 되지만 `%`, `vh`, `vw`, `em` 등의 상대적 단위로 연산을 할 때는 `calc()`로 연산해야 한다.  

`/` 나누기 연산을 할 때는 오류가 날 수도 있으니 괄호를 사용하도록 하자

[https://heropy.blog/2018/01/31/sass/](https://heropy.blog/2018/01/31/sass/)
