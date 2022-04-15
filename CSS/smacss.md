# SMACSS

SMACSS는 Scalable and Modular  Arcitecture CSS의 줄임말로 확장형 모듈식으로 CSS를 구성하는 기법이다. CSS를 Base, Layout, Module, State, Theme 이렇게 다섯가지 카테고리로 나누어 스타일을 정리한다. 

### 1. Base

기초 스타일을 지정하는 부분으로 default.css, reset.css를 적용하는 부분이 Base에 포함된다. 아이디나 클래스 선택자를 사용하는 것이 아니라 기본 태그의 스타일을 지정하는 것이다. 이때 !important는 허용되지 않는다.

```css
html, body, form {margin:0;padding:0;}
input[type=text] {border:1px solid #999;}
a {color:#000;}
a:hover {color:#666;}
```

### 2. Layout

큰 틀의 레이아웃, 다양한 요소들을 구별할 때 사용한다. 주요 컴포넌트에는 header, footer, aside, container, content등이 있고, 하위 컴포넌트에는 list, item, form 등이 있다. 주요 컴포넌트는 id를 사용하고, 하위 컴포넌트는 class를 사용하여 스타일을 지정한다. 클래스 명을 사용할 때는 `l-` 또는 `layout-`을 붙인다. 

```css
#content {width:80%;float:left;}
#aside {width:20%}

.l-fixed #content {
  width: 600px;
  margin-right: 10px;
}
.l-fixed #aside {
  width: 200px
}
```

### 3. Module

레이아웃 안의 더 작은 부분을 가리킬 때 module을 사용하는데 이는 재사용을 가능하게 하기 위함이다. 버튼, 위젯, 배너 등이 이 부분에 포함될 수 있다. 각 모듈은 독립적일 수 있도록 설계해야하며 다른 곳에서도 사용할 수 있어야 한다. 재사용을 해야하기 때문에 id선택자는 사용하지 않고, class 선택자를 사용한다. 모듈안의 엘리먼트에 접근하려면 child 선택자를 이용해 접근한다. 

```html
<div class="box">
  <span class="box-name"> ... </span>
  <span class="box-items"> ... </span>
</div>
```

```css
.box { ... }
.box-name { ... }
.box-items { ... }
.box-items > span { ... }
```

### 4. State

툴팁, 아코디언 등 어떤 요소의 상태가 열리거나 닫히는 등의 상태 변화가 일어나는 경우에 표현하는 스타일이다. 클래스를 사용하며 is- 또는 s- 접두사를 사용한다. 상태 스타일은 복잡한 상황에서 !important를 사용할 수 있다. 

```html
<!-- 레이아웃 요소, 접힌 상태 -->
<div id="header" class="is-collapsed">
  <form>
    <!-- 모듈, 오류 상태 -->
    <div class="msg is-error">
      There is an error!
    </div>
    <!-- 연관된 라벨이 숨겨진 상태 -->
    <label for="search" class="is-hidden">Search</label>
    <input type="text" id="search">
  </form>
</div>
```

- `#header`는 레이아웃 요소임을 알 수 있으며, .is-collapsed로 접힌 상태임을 알 수 있다.
- `.msg`는 모듈이며 .is-error로 오류 상태임을 알 수 있다.
- **`#searchbox`** 연관된 라벨은 숨겨져 있는 것을 알 수 있다. (`.is-hidden`)

### 5. Theme

사이트 전체의 look and feel을 제어한다. 색상이나 이미지를  다룰 때 사용하는데 테마 스타일의 규칙만 모아서 분리한다. 이미 스타일링된 요소 뒤에 다시 재선언하여 테마만 입히는 방식이다.

```css
/* main.css */
.box {
  border: 1px solid;
}

/* theme.css - main.css 뒤에서 읽도록 적용 */
.box {
  border-color: blue;
}
```

### 장점

- 5개의 카테고리로 범주화하기 때문에 알아보기 쉽고 재사용성이 증가하는 동시에 코드가 간결해진다.
- 또 클래스명을 통해 역할을 쉽게 예측할 수 있다.

### 단점

- 규칙에 대한 종속성이 있다.
- 카테고리의 기준이 모호해질 수 있다.
- 범주화하기 때문에 CSS를 사용하기 복잡해질 수 있다.

---

출처

[https://blog.illunex.com/20201106-2/](https://blog.illunex.com/20201106-2/)

[https://chlolisher.tistory.com/11](https://chlolisher.tistory.com/11)

[https://whales.tistory.com/33](https://whales.tistory.com/33)
