# em, rem, px

절대 단위는 어떤 다른 상황에서도 영향을 받지 않고, 항상 고정된 길이를 가진다. 반면 상대 단위는 어떤 기준에 따라 값이 변할 수 있는 단위들이다.


+ 절대 단위: px
/상대 단위: %, v*, em, rem


+ 부모요소의 사이즈에 따라: %, em
/브라우저에 따라: v*, rem

+ 요소의 너비와 높이에 따라: %, v*
/폰트사이즈에 따라: em, rem

+ em: relative to parent element
/rem: relative to root element

우선 em과 rem은 폰트사이즈에 따라 결정되는 단위이다. 

만약 해당 요소의 font-size:16px인 경우 

0.5em =16px * 0.5 = 8px

1em = 16px * 2 = 16px

만약 font-size:160px로 늘린 경우 

0.5em = 160px * 0.5 = 80px

1em = 160px * 1 = 160px

rem도 em과 마찬가지로 font-size를 기준으로 결정되는 단위이다. 그러나 차이점은 rem은 html요소의 font-size를 기준으로 하고, em은 현재 자신의 요소 font-size를 기준으로 한다는 것이다. 기본적으로 font-size는 16px로 설정된다. html의 font-size가 16px인 상황에서 다음과 같은 속성을 가진 div가 안에 들어 있다고 하자.

```css
div{
	font-size: 12px;
	padding-left: 1rem; /* 16px */
	padding-right: 1em; /* 12px */
}	
```

왼쪽 padding은 1rem으로 설정하고 오른쪽 padding은 1em으로 설정했는데 둘의 크기는 다르게 나타난다. rem은 최상단의 font-size를 기준으로 하기 때문에 html의 font-size인 16px과 1이 곱해져 왼쪽 패딩은 16px이 된다. 오른쪽 패딩은 해당 요소의 font-size를 기준으로 하기 때문에 12px * 1 = 12px이 된다. 

만약 위의 예시에서 div요소에 font-size를 지정하지 않고 1em이라고 지정하면 16px이 된다. font-size가 정의되지 않으면 부모의 font-size를 기준으로 하기 때문이다. 만약 복잡한 계층적 구조에서 em이 빈번하게 사용된다면 변동상황에서 어떤 값으로 계산될 지 예측하기 어렵기 때문에 꼭 필요한 경우에만 em을 사용하는 것이 좋다.
