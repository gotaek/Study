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

# SCSS

## variable&nesting

scss폴더에 _variables.scss파일을 생성

```scss
$bg: red; /*변수 설정*/
```

```scss
@import "_variables";

h2{
	color:$bg;
}
/* nesting */
.box{
	&:hover{
		background:green;
	}
	margin-top:20px;
	h2{
		color:blue;
	}
	button{
		color:red;
	}
}

```

## Mixins

scss functionality를 재사용할 수 있도록 함

어떤 종류의 arguments를 mixin에 보낼 때 사용

즉, 상황에 따라 다르게 코딩을 하고 싶으면 사용

### 예시 1

_mixins.scss파일을 생성

```scss
@mixin link($color) {
  text-decoration:none;
	display:block
	color:$color/*변수를 통해 설정 가능*/
}
```

```scss
@mixin link($word){
	text-decoration:none;
	display:block;
	@if $word=='odd'{
		color:blue;
	}@else{
		color:red;
	}
}
```

```scss
.box{
	@include link('odd')
}
```

### 예시 2 (responsive)

```scss
$minIphone: 500px;
$maxIphone: 690px;
$minTablet: $minIphone + 1;
$maxTablet: 1120px;

@mixin responsive($device) {
  @if $device == "iphone" {
    @media screen and (min-width: $minIphone) and (max-width: $maxIphone) {
      @content;
    }
  } @else if $device == "tablet" {
    @media screen and (min-width: $minTablet) and (max-width: $maxTablet) {
      @content;
    }
  } @else if $device == "iphone-l" {
    @media screen and (max-width: $minIphone) and (max-width: $maxIphone) and (orientation: landscape) {
      @content;
    }
  } @else if $device == "ipad-l" {
    @media screen and (min-width: $minTablet) and (max-width: $maxTablet) and (orientation: landscape) {
      @content;
    }
  }
}
```

```scss
@import "_mixins";

h1 {
  color: red;
  @include responsive("iphone") {
    color: yellow;
  }
  @include responsive("iphone-l") {
    font-size: 60px;
  }
  @include responsive("tablet") {
    color: green;
  }
}
```

## Extends

같은 코드를 중복하고 싶지 않을 때 사용

다른 코드를 확장하거나 코드를 재사용하려고 할 때 사용

_buttons.scss 생성
```scss
@import "_buttons"
a{
	@extend:%button;
	text-decoration:none;
}
button{
	@extend:%button;
	border:none;
}
```
```scss
@import "_buttons"
a{
	@extend:%button;
	text-decoration:none;
}
button{
	@extend:%button;
	border:none;
}
```

[https://heropy.blog/2018/01/31/sass/](https://heropy.blog/2018/01/31/sass/)