# Pseudo-elements

가상선택자는 기본선택자 뒤에**:**(콜론)을 붙인 가상 클래스,

**::**(콜론두개)을 붙인 가상 요소로 요소의 특정 부분을 선택합니다.

– 가상클래스(Pseudo-Class)는,별도의 class를 지정하지 않아도 지정한 것 처럼요소를 선택할 수 있습니다.

– 가상요소(Pseudo-Element)는, 가상클래스처럼 선택자(selector)에 추가되며,

존재하지 않는 요소를 존재하는 것처럼 부여하여 문서의 특정 부분 선택이 가능합니다.

### 가상 요소

선택자에 의해 선택된 요소의 특정 부분에 스타일을 적용한다. 가상 요소는 콜론(:)을 2개 사용하지만, 1개 사용해도 대부분 브라우저에서 정상적으로 작동한다.

**::first-letter**로 첫 번째 글자를 선택한다.

```css
p::first-letter {
    color: red;
}
```

<p> 태그 요소의 첫 번째 글자의 스타일을 빨간색으로 적용한다.

문장부호('-', '_', 따옴표, 괄호 등)로 시작할 경우 그 문장 부호부터 본문의 첫 번째 글자까지 선택한다.

예를들어, 요소의 내용이 <p>"korea seoul"</p>이라면 "k(두글자)가 선택된다.

**::first-line**로 첫 번째 줄을 선택한다.

```css
p::first-line {
    color: red;
}
```

<p> 태그 요소의 첫 번째 줄의 스타일을 빨간색으로 적용한다.

**::before**로 시작 부분을 선택한다.

```css
p::before {
    content: "korea";
    color: red;
}
```

<p> 태그 요소 앞에 korea 글자를 삽입하고 스타일을 빨간색으로 적용한다.

**::after**로 끝 부분을 선택한다.

```css
p::after {
    content: "korea";
    color: red;
}
```

<p> 태그 요소 뒤에 korea 글자를 추가하고 스타일을 빨간색으로 적용한다.

**::selection**로 드래그한 글자를 선택한다.

```css
::selection {
    color: red;
}
```

드래그로 선택한 글자의 스타일을 빨간색으로 적용한다.

'color', 'background-color', 'cursor', 'caret-color', 'outline-*', 'text-decoration-*', 'text-shadow' 속성만 적용할 수 있다.

### 가상 클래스와 가상 요소의 순서

가상 클래스와 가상 요소를 함께 이용할 경우에는 **가상 클래스 : 가상 요소** 순서를 지켜야 한다.

```css
p:hover:before {
    content: "korea";
    color: red;
}
```

<p> 태그 중 마우스가 올라간 요소 앞에 korea 글자를 삽입하고 스타일을 빨간색으로 적용한다.

출처:

[https://blog.pages.kr/2488](https://blog.pages.kr/2488)

[pages.kr 날으는물고기 <º))))><]

content는 스크린 리더가 읽을 수 있음

[http://blog.hivelab.co.kr/공유before와after-그들의-정체는/](http://blog.hivelab.co.kr/%EA%B3%B5%EC%9C%A0before%EC%99%80after-%EA%B7%B8%EB%93%A4%EC%9D%98-%EC%A0%95%EC%B2%B4%EB%8A%94/)
