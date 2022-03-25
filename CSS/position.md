# position

position은 문서 상에 요소를 배치하는 방법인데 값으로는 static, relative, absolute, fixed, sticky가 있다. position을 사용한다고 위치가 직접적으로 지정되는 것이 아니라 기준을 잡아준다고 생각하면 된다. position으로 기준을 잡고,  top, bottom, left, right 속성을 사용하여 최종 위치를 결정하는 것이다. 따라서 top, bottom, left, right를 사용하지 않고 요소가 일반적인 흐름에 따라 배치되는 position 키워드 값을 사용할 경우에 레이아웃의 변화를 느끼지 못할 것이다.

## static

요소를 일반적인 흐름에 따라 배치하는 것이고, 커다란 특징은 없기 때문에 자주 사용하는 키워드는 아니다.

## relative

요소를 일반적인 흐름에 따라 배치하고, 원래 자신의 위치를 기준으로 잡는 것이다. 기준을 잡고 위치를 변경시킨다고 하더라도 다른 요소들은 영향을 받지 않는다. position:relative는 또한 다른 용도로도 사용되는데 그것은 자식의 position이 absolute일 때 부모의 position을 relative로 설정함으로 자식의 기준이 되도록 한다. 자세한 것은 absolute에서 설명한다. 

## absolute

요소를 일반적인 흐름에서 제거하기 때문에 주변의 요소들이 영향을 받을 수 있다. 가장 가까운 조상의 position값이 static이 아닌 경우에 그 부모 요소를 기준으로 하여 상대적으로 요소를 배치할 수 있는 키워드 값이다. 부모 요소의 position이 static이 아닌 경우 기준이 될 수 있지만 일반적으로는 자식 요소에서 absolute를 사용할 때 부모 요소는 position:relative로 설정한다. 만약 부모, 조상에 position:relative가 없다면 <body>태그를 기준으로 한다.

## fixed

fixed는 요소를 일반적인 흐름에서 제거하여 뷰포트를 기준으로 하는 키워드 값이다. 따라서 스크롤을 내려도 처음 위치했던 곳에 그대로 위치하는 것을 확인할 수 있다. 그러나 fixed를 설정한 요소의 부모 요소에서 `transform`, `perspective`, `filter` 속성 중 어느 하나라도 `none`이 아니라면 그 조상을 기준으로 삼기 때문에 주의해야 한다.

## sticky

일반적인 문서 흐름에 따라 배치 되며 top, bottom, left, right 값을 준다고 바로 그 위치로 배치되는 것이 아니라 일반적인 문서 흐름으로 처음 배치 된 후 스크롤을 내리다가 뷰포트에서 top, bottom, left, right로 준 요건을 만족시킨다면 fixed되는 것이다. 만약 만족시키지 않는다면 요건을 충족할 때까지 position: relative로 배치된다. 

---

출처

[https://developer.mozilla.org/ko/docs/Web/CSS/position#형식_정의](https://developer.mozilla.org/ko/docs/Web/CSS/position#%ED%98%95%EC%8B%9D_%EC%A0%95%EC%9D%98)
