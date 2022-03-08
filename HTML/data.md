# ****data- 속성****

data속성은 특정 데이터를 DOM요소 안에 저장하기 위한 속성이다.

```html
<article
  id="electriccars"
  data-columns="3"
  data-index-number="12314"
  data-parent="cars">
...
</article>
```

위와 같이 `data-` 뒤에 어떤 문자열을 적어주는 방식으로 화면에 안보이게 어떤 정보들을 엘리먼트에 저장할 수 있다. 

자바스크립트를 사용해 데이터에 접근하려면 dataset을 사용하면 되는데 이때 `-`

를 사용했던 속성은 camelCase로 변환되어 저장된다.

```jsx
var article = document.getElementById('electriccars');

article.dataset.columns // "3"
article.dataset.indexNumber // "12314"
article.dataset.parent // "cars"
```

데이터셋 속성은 검색엔진에서 인덱싱을 하지 않는다. 따라서 검색엔진에 노출할 내용이나, 태그에 넣어야할 컨텐츠를 데이터셋 속성으로 표시하면 안된다. 자바스크립트를 통해 접근을 할 수 있기 때문에 노출되기에 민감한 정보를 사용할 때는 사용하지 않는 것이 좋다. 그러나 간결하게 데이터를 저장할 수 있기 때문에 가벼운 데이터를 저장하기에는 편리하다.

출처

[https://github.com/baeharam/Must-Know-About-Frontend/blob/main/Notes/html/data.md](https://github.com/baeharam/Must-Know-About-Frontend/blob/main/Notes/html/data.md)
