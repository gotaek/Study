# display

CSS에서 어떤 요소의 display를 설정할 때 `block`, `inline`, `inline-block`, `none` 이렇게 4가지 중 선택할 수 있는데 하나한 알아보자. display 속성은 화면에 렌더링될 때 요소가 얼마만큼의 크기를 가질 것인지를 설정하는 것이라고 볼 수 있다. 

# block

```html
<address>, <article>, <aside>, <blockgquote>, 
<canvas>, <dd>, <div>, <dl>, <hr>, <header>, <form>,
<h1>, <h2>, <h3>, <h4>, <h5>, <h6>, <table>, <pre>, <ul>, <p>, <ol>, <video>
```

위와 같은 태그들이 `display: block` 속성을 가지고 있다. 

가장 먼저 알아볼 값은 block이다. 해당 값은 div 태그의 기본값으로 `width`가 100%를 차지하게 한다. 

block은 `height`, `width`값을 지정할 수 있으며 `margin`, `padding`도 지정할 수 있다. 사이즈를 쉽게 조절할 수 있기 때문에 많이 사용하는 속성 값이다.

# inline

```html
<a>, <i>, <span>, <abbr>, <img>, <strong>, <b>, <input>, 
<sub>, <br>, <code>, <em>, <small>, <tt>, <map>, <textarea>, 
<label>, <sup>, <q>, <button>, <cite>
```

주로 텍스트를 삽입할 때 많이 사용되는 속성값이다. 줄바꿈이 일어나지 않고, 안의 컨텐츠를 감쌀 정도로만 크기가 지정된다. 

`margin-top`, `margin-bottom`은 값을 설정해도 적용이 되지 않지만 `margin-left`, `margin-right`는 적용되는 것을 확인할 수 있다. 따라서 상,하 여백을 설정하기 위해서는 `line-height`를 사용해야 한다. 또한 `width`와 `height`의 값을 아무리 높이거나 낮혀도 컨텐츠가 포함된 만큼만 `width`와 `height`가 지정된다. 

# inline-block

`inline` 과 block을 적절히 섞은 속성 값이라고 볼 수 있다. 일단 맨처음에는 inline처럼 줄바꿈이 일어나지 않고, 컨텐츠 영역만큼 크기가 잡히는 inline의 속성값과 유사하다. 그러나 block처럼 `height`, `width`, `margin` 등을 설정하여 크기를 변경할 수 있다. 

block과 inline을 함께 사용해야 할 경우 block을 바깥에 위치하고 inline을 안쪽에 위치해야한다. block이 inline보다 넓은 개념이기 때문이다. 

```html
<p><span>Hello World!</span></p>
```

---

출처 및 참고

[https://seungwoohong.tistory.com/23](https://seungwoohong.tistory.com/23)
