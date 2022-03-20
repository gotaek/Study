# box-sizing

css 박스 모델에서 height, width 속성을 이용해 높이나 너비를 설정하면 이는 content 영역에 적용된다. 즉, border과 padding을 포함한 범위가 아닌 것이다. 그래서 단순히 width만 변경할 것이 아니라 border과 padding의 크기도 고려해야 원하는 크기를 얻을 수 있다.

`box-sizing`이라는 속성을 사용하면 편하게 스타일링을 할 수 있는데 `box-sizing` 속성에는 `content-box`와 `border-box`라는 키워드가 있다. `content-box`는 width, height의 속성이 content 영역에만 한정되는 것인 반면 `border-box`는 content, padding, border까지 포함하여 width, height를 고려한다. 그래서 원하는 스타일링을 위해서는 `border-box`를 사용하는 것이 편하다. 

