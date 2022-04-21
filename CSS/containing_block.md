
# 컨테이닝 블록

만약 어떤 요소의 width를 50%로 지정했다고 하자. 그렇다면 어떤 요소를 기준으로 width를 계산하는 것일까? 그 기준이 부모 요소라고 판단할 수 있지만 사실 모두 부모 요소가 기준이 되는 것은 아니다. 요소들은 컨테이닝 블록을 기준으로 `width`, `height`, `padding`, `margin` , `top`, `right`, `bottom`, `left`들이 결정되고는 한다.  또 크기 뿐만 아니라 요소의 위치를 정하는 기준이 될 수 있는 것이 컨테이닝 블록이다. 

**상황에 따른 컨테이닝 블록**

1. `position`이 `absolute`인 경우에는 `static`제외한 가장 가까운 조상
2. `position`이 `fixed`인 경우에는 뷰포트
3. `position`이 `static`, `relative`, `sticky` 중 하나인 경우에는 가장 가까운 조상 블록 컨테이너(`inline-block`, `block`, `list-item` 등의 요소) 또는 가장 가까우면서 서식 맥락을 형성하는 조상 요소(`table`, `flex`, `grid`, 아니면 블록 컨테이너 자기 자신)

만약 어떤 요소의 부모 display가 inline이라면 부모 요소가 컨테이닝 블록이 되는 것이 아니라 더 위의 조상 중에서 컨테이닝 블록이 될 수 있는 것을 찾는다. 

[https://developer.mozilla.org/ko/docs/Web/CSS/Containing_block](https://developer.mozilla.org/ko/docs/Web/CSS/Containing_block)
