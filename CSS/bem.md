# BEM

BEM은 Block Element Modifier의 약자로 OOCSS, SMACSS보다 더 많이 사용되는 방법론이다. BEM을 사용한다면 id는 사용하지 않고, class만 사용한다는 것에 주의하자. 지금부터 block, element, modifier가 무엇인지, 어떤 방식으로 작명하는 것이 효율적인지 알아보자.

## Block

재사용이 가능한 독립적인 컴포넌트를 block이라고 한다. 

로고 같은 경우는 웹 페이지에서 재사용될 일이 많기 때문에 block이라고 할 수 있다. header, aside, content, footer 등이 독립적으로 존재해야 하기 때문에 block이 된다. 이 때 block은 환경에 영향을 받으면 안되기 때문에 여백이나 위치를 설정할 수 없다. 

만약 block 안에 또 다른 block이 들어간다면 그냥 클래스 이름을 지정하면 된다. 

```html
<div class="header">
	<div class="menu">...</div>
	<div class="search">...</div>
</div>
```

## Element

element는 block을 구성하는 요소 단위로 의존적인 성격을 가진다. 자신이 속한 블록 안에서만 존재하기 때문에 다른 곳에서 재사용할 수 없는 것들을 element라고 한다. 클래스 이름은 자신을 포함하고 있는 block 뒤에 __를 붙인 후 자신의 이름을 붙여 이름을 짓는다. 예를 들면 이런식이다. `.header__title` element안에 또 다른 element가 존재할 수 있는데 이 경우에 계속 `__`를 붙이는 것은 아니다. 자신을 포함하는 block만 `__`앞에 붙여주면 된다. 

```html
<form class="search-form">
  <div class="search-form__content">
      <input class="search-form__content__input"/>
      <button class="search-form__content__button">Search</button>
  </div>
</form>
```

위처럼 중첩되는 것이 아니라 아래처럼 블록이름 다음에 __자신 이런식으로 사용하면 된다.

```html
<form class="search-form">
	<div class="search-form__content" >
		<input class="search-form__input" />
		<button class="search-form__button">Search</button>
	</div>
</form>
```

이때 주의해야 할점은 다른 블록/앨리먼트 요소에 의존하는 선택자를 사용하면 안된다는 것이다. `.search-form .search-form__input` 이렇게 선택하는 것이 아니라 `.search-form__input`이렇게 선택하면 된다. 

## Modifier

modifier는 block이나 element의 속성을 나타낼 때 사용한다. `block—modifier`, `block__element—modifier`같은 형태로 사용할 수 있다. modifier 앞에 —를 붙여주는 것이다. `class=”block__element—modifier”`이렇게 단독으로 사용될 수 없고 `class=”block__element block__element—modifier”` 기본 블록이나 요소이름을 설정한 후 뒤에 modifier를 추가하는 형태로 사용한다. 

modifier에는 boolean 타입과 key-value 타입이 있다. `form__button--focused` boolean 타입인데 이름만 봐서 form 블록의 button 엘리먼트가 focused 되었을 때 사용하는 속성들이라는 것을 쉽게 알아차릴 수 있다. 

key-value 형식에서는 하이픈으로 키와 값을 연결하여 사용한다. `title—color-gray` 어떤 태그가 이 클래스를 가진다면 title블록임을 알 수 있고, color는 gray로 설정되리라 알아차릴 수 있다. 하이픈 하나로 key와 value를 구분해 modifier로 사용한 것이다. 

### 장점

- html문서를 보지 않아도 클래스 명만으로도 구조를 어느 정도 파악할 수 있다.
- SASS의 `&` 과 함께 사용할 때 매우 편리하다.
- block, element, modifier라는 개념을 사용하기 때문에 클래스 명의 중복을 쉽게 방지할 수 있다.

### 단점

- 하위 요소로 들어갈수록 클래스명이 지나치게 길어져 복잡할 수 있다.

---

참고

[https://chlolisher.tistory.com/11](https://chlolisher.tistory.com/11)

[https://nykim.work/15](https://nykim.work/15)
