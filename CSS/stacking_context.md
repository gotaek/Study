# z-index & 쌓임 맥락

# z-index가 없는 경우

일단 z-index에 대해 알아보기 전에 z-index가 적용되지 않은 블록들이 겹쳤을 때 어떤 블록이 가장 위에 오는 지부터 알아보자. MDN에 따르면 다음과 같은 순서로 아래에서부터 쌓이기 시작한다고 했다.

1. 뿌리 엘리먼트의 배경과 테두리
2. 자식 엘리먼트들은 HTML에서 등장하는 순서대로
3. position이 지정된 자식 엘리먼트들은 HTML에서 등장하는 순서대로

즉, 가장 아래에 부모 요소가 쌓이고, 그 위에 자식 엘리먼트들이 쌓인다. 이 때 같은 부모를 가진 자식 엘리먼트들 사이에서는 HTML 문서에서 위에 있는 것이 아래에 깔리겠다. 그리고 그 위에는 position이 지정된 자식 엘리먼트가 깔린다.

# z-index가 있는 경우

위와 같이 쌓이는 규칙에서 벗어나 임의로 쌓임 순서를 정하고 싶다면 z-index라는 속성을 이용하면 된다. z-index란 어떤 요소에 z-index:1 형태처럼 지정하여 z-index 값에 따라 정렬하여 가장 높은 값이 가장 위에 오도록 한다. 그러나 주의해줘야 할 점이 있는데 z-index를 사용하기 위해서는 position속성을 지정해줘야 한다. 즉,  엘리먼트의 position을 static이 아닌 값으로 설정하고 z-index를 함께 사용해야 원하는 대로 쌓임 순서를 만들 수 있다.

z-index값을 음수로 지정할 수 있는데 이렇게 지정된 요소는 부모보다 뒤에 위치한다. z-index의 기본 값은 0이기 때문이다. 따라서 부모보다 작은 수를 가지기 때문에 뒤에 위치하게 되는 것이다. 만약 부모의 z-index 값이 자식의 z-index값보다 더 작아지게 되면 다시 뒤에 위치한다. 

# 쌓임 순서

그래서 z-index가 있는 경우와 z-index가 없는 경우를 합쳐서 쌓임 순서를 정리하자면 아래와 같은 순서로 아래에서부터 쌓이기 시작한다.

1. 쌓임 맥락의 뿌리(root) 요소. (html요소)
2. position 값이 있고 z-index 값이 음수인 요소(와 자식들). (z-index 값이 높은 요소가 앞에 놓인다. 값이 같으면 HTML에 나타난 순서에 따라 나타난다.)
3. position 값이 없는 요소(HTML에서 나타나는 순서를 따른다).
4. position 값이 있고 z-index 값이 auto인 요소(와 그 자식들). (HTML에서 나타나는 순서에 따라)
5. position 값이 있고 z-index 값이 양수인 요소(와 그 자식들). (z-index 값이 높은 요소가 앞에 놓인다. 값이 같으면 HTML에 나타난 순서에 따라 나타난다.)

---

그러나 위의 순서들은 하나의 쌓임 맥락에서 적용되는 순서이다. 쌓임 맥락이란, HTML 요소들에 사용자를 바라보는 기준으로 가상의 z축을 생성하여 3차원 개념으로 보는 것이다.

약간 이해하기 어려울 수 있겠지만 쌓임 순서를 만드는 범위라고 생각할 수 있다. 각각의 쌓임 맥락은 독립적이라 어떤 쌓임 맥락을 포함하는 더 큰 쌓임 맥락이 존재한다고 하더라도 영향을 주지 않고 부모는 자식의 쌓임 맥락을 하나의 단위로 인식한다. 

쌓임 맥락의 특징을 다음과 같이 정리할 수 있겠다.

- 쌓임 맥락이 다른 쌓임 맥락을 포함할 수 있고, 함께 계층 구조를 이룹니다.
- 쌓임 맥락은 형제 쌓임 맥락과 완전히 분리됩니다. 쌓임을 처리할 땐 자손 요소만 고려합니다.
- 각각의 쌓임 맥락은 독립적입니다. 어느 요소의 콘텐츠를 쌓은 후에는 그 요소를 통째 부모 쌓임 맥락 안에 배치합니다.

# 쌓임 맥락

쌓임 맥락이 생성되는 조건은 아주 많은데
그 중 기억하면 좋을 것은 이 정도가 될 것 같다.

- position이 relative 또는 absolute이면서 z-index가 auto가 아닌 요소
- position이 fixed 또는 sticky인 요소
- opacity가 1보다 작은 요소
- transform이 none이 아닌 요소

---

![https://developer.mozilla.org/@api/deki/files/913/=Understanding_zindex_04.png](https://developer.mozilla.org/@api/deki/files/913/=Understanding_zindex_04.png)

```html
<div>div #1</div>
<div>div #2</div>
<div>div #3
  <div>div #4</div>
  <div>div #5</div>
  <div>div #6</div>
</div>
```

위의 그림은 div #1, div #2, div #3이 하나의 쌓임 맥락을 가지고, div #3, div #4, div #5, div #5가 하나의 쌓임 맥락을 가지게 된다. 따라서 div #4의 z-index값이 div #1의 z-index 값보다 크더라도 자식 쌓임 맥락과 부모 쌓임 맥락은 독립적이기 때문에 아래에 위치하게 된다.

---

출처

https://github.com/baeharam/Must-Know-About-Frontend/blob/main/Notes/css/z-index.md

https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context
