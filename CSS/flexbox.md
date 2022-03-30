

# Flexbox

오랫동안 웹 페이지 레이아웃을 float, inline-block등을 사용해서 잡아왔지만 flexbox가 나오면서 그 방법들을 사용할 이유들이 사라졌다.

- 부모 요소 내부에 포함된 블록 콘텐츠를 세로로 중심부에 맞추기.
- 사용 가능한 너비와 높이에 관계없이 하나의 컨테이너에 포함된 모든 자녀 요소가 주어진 너비와 높이를 똑같은 크기로 점유하기.
- 다단 레이아웃에 포함된 모든 단이 서로 다른 크기의 콘텐츠를 포함하고 있더라도 동일한 높이로 채택하기.

즉 쉽게 레이아웃을 설정하는데 도움을 주는 것이 flexbox이다.

# main-axis & cross-axis

먼저 flexbox를 사용하기 위해서는 어떤 요소에 `display: flex`로 설정해야 한다. 기본 축 (main-axis)는 가로 방향으로 웹 페이지를 가로지르는 축이다. 그리고 교차 축(cross-axis)는 기본 축에 수직이 되는 방향의 축이다. 이는 기본적으로 설정되는 값으로 만약 flex-direction을 변경하면 반대가 된다. 

우선 기본적으로 `flex-direction`은 `row`이다. 이때의 축 방향은 위의 설명과 같다. 그러나 `flex-direction:column`으로 하면 기본 축이 세로 방향이 되고, 교차 축이 가로 방향이 된다. 

# justify-content

`justify-content`는 기본 축에서 flex item들을 어떻게 배치할 지를 정한다. `justify-content`에는 다음과 같은 값을 가질 수 있다.

1. `flex-start` : 기본 설정으로, 플렉스 요소는 플렉스 컨테이너의 앞쪽에서부터 배치됩니다.
2. `flex-end` : 플렉스 요소는 플렉스 컨테이너의 뒤쪽에서부터 배치됩니다.
3. `center` : 플렉스 요소는 플렉스 컨테이너의 가운데에서부터 배치됩니다.
4. `space-between` : 플렉스 요소는 요소들 사이에만 여유 공간을 두고 배치됩니다.
5. `space-around` : 플렉스 요소는 앞, 뒤, 그리고 요소들 사이에도 모두 여유 공간을 두고 배치됩니다.
6. `space-evenly`: 플렉스 요소 앞, 뒤, 그리고 요소들 사이에서 모두 여유 공간을 두고 배치되지만 모두 같은 간격을 가진다.


# align-items

`align-items`는 교차 축에서 flex item들을 어떻게 배치할 지를 정한다. 만약 `flex-direction`이 변경되면 당연히 메인 축과 교차 축도 다르기 때문에 아래의 속성 값들도 축에 따라 다르게 나타난다.

1. `stretch`: 아이템들이 수직축 방향으로 끝까지 쭈욱 늘어납니다.
2. `flex-start`: 아이템들을 시작점으로 정렬합니다. `flex-direction`이 row(가로 배치)일 때는 위, column(세로 배치)일 때는 왼쪽이에요.
3. `flex-end`: 아이템들을 끝으로 정렬합니다. `flex-direction`이 row(가로 배치)일 때는 아래, column(세로 배치)일 때는 오른쪽이에요.
4. `center`: 아이템들을 가운데로 정렬합니다.
5. `baseline`: 아이템들을 텍스트 베이스라인 기준으로 정렬합니다.

# flex-wrap

flex 요소를 담고 있는 컨테이너의 크기가 변경될 때 그 안의 flex요소들을 어떻게 배치할 지에 대한 것으로 반응형 웹페이지를 만들 때 중요한 역할을 한다.

속성 값으로는 `no-wrap`, `wrap`, `wrap-reverse`가 있다. `no-wrap`은 컨테이너의 크기가 줄어들어도 flex요소의 줄바꿈이 일어나지 않고 컨테이너의 넓이를 넘어서서 배치된다. `wrap`은 만약 flex요소가 배치될 공간이 없으면 다음 줄에 배치된다. `wrap-reverse`는 flex요소가 배치될 공간이 없을 시 아래줄에 배치되는 것이 아니라 위에 배치된다.

# flex-flow

`flex-direction`과 `flex-wrap`을 한꺼번에 지정할 수 있는 단축 속성이다. 반응형으로 웹페이지를 제작할 일이 많을 터이니 다음과 같이 사용하도록 하자.

```css
flex-flow: row wrap;
```

# align-content

`flex-wrap:wrap`으로 설정해서 flex요소들이 두줄에 걸쳐 나올 때 사용하면 좋을 속성이다. `justify-content`에서 `space-between`, `space-around`, `space-evenly` 등의 값이 메인 축에 있는 flex요소들의 간격들을 조정해주는 것이었다면 align-content는 두줄 이상으로 flex 요소가 되었을 때 그 줄 들의 간격을 조정하는 것이다. 다음과 같은 속성값들을 가질 수 있다.

1. `stretch` : 기본 설정으로, 플렉스 라인의 높이가 남는 공간을 전부 차지하게 됩니다.
2. `flex-start` : 플렉스 라인은 플렉스 컨테이너의 앞쪽에 뭉치게 됩니다.
3. `flex-end`: 플렉스 라인은 플렉스 컨테이너의 뒤쪽에 뭉치게 됩니다.
4. `center` : 플렉스 라인은 플렉스 컨테이너의 가운데에 뭉치게 됩니다.
5. `space-between` : 플렉스 라인은 플렉스 컨테이너에 고르게 분포됩니다.
6. `space-around` : 플렉스 라인은 플렉스 컨테이너에 고르게 분포됩니다. 단, 양쪽 끝에 약간의 공간을 남겨둡니다.
7. `space-evenly`: 플렉스 요소 앞, 뒤, 그리고 요소들 사이에서 모두 여유 공간을 두고 배치되지만 모두 같은 간격을 가진다.

# gap

세부적인 레이아웃을 잡기 위해서 간격을 지정할 수 있어야 한다.

1) 컨테이너와 컨텐츠의 간격

2) 컨텐츠 간의 간격

그러나 margin을 이용해서 요소들간의 간격을 지정하면 컴포넌트 간의 배치하고 컨트롤하는데 문제가 생길 수 있다. gap은 엘리먼트 요소들 사이에만 공간을 만들기 때문에 gap을 사용하면 좋다. margin의 경우 주변에 요소가 있던지 말던지 그냥 지정한 값을 가지는데 gap의 경우에는 인접한 요소가 없다면 공간을 만들지 않는다.

```css
gap: 10px 5px;
```

부모 요소에 다음 처럼 설정하면 상하 10px 좌우 5px gap이 생성된다.

# flex-grow

만약 형제요소로 렌더링 된 모든 `flex-item` 요소들이 동일한 `flex-grow` 값을 갖는다면, `flex-container` 내부에서 동일한 공간을 할당받는다. 하지만 `flex-grow` 값으로 다른 소수값을 지정한다면, 그에 따라 다른 공간값을 나누어 할당받게 된다. 

`flex-basis`보다 커질 수 있는 지를 설정해주는 속성인데 0으로 설정한 경우 `flex-basis`만큼 크기를 갖거나 컨텐츠의 크기만큼의 너비를 가지지만 1로 변경할 경우 부모의 너비를 모두 채워 위치한다.

# flex-shrink

`flex-shrink` 속성은 플렉스박스에 `flex-wrap: wrap` 속성을 부여한 경우 적용되지 않는다. 요소들의 너비 합이 컨테이너의 너비를 넘어설 경우 컨테이너의 너비를 넘지 않고 각각 요소마다 어느 정도로 수축할 것인지 정할 수 있는 속성이다. 

이는 `flex-grow`와 반대로 아이템이 `flex-basis`의 값보다 작아질 수 있는지를 결정한다. 기본값은 1로 되어있기 때문에 `flex-basis`보다 크기가 작아질 수 있다. 그러나 0으로 `flex-shrink`를 설정하면 고정 폭을 가질 수 있다.

# flex-basis

`flex-basis`는 Flex 아이템의 기본 크기를 설정한다. (`flex-direction`이 `row`일 때는 너비, `column`일 때는 높이). 기본값 auto로 설정하면 해당 요소의 width값이 된다. **`flex-basis`** `box-sizing`을 따로 지정하지 않는다면 콘텐츠 박스의 크기를 변경합니다.

# flex

`flex-grow`, `flex-shrink`, `flex-basis`를 한 번에 쓸 수 있는 축약형 속성이다.

```css
.item {
	flex: 1;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: 0%; */
	flex: 1 1 auto;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: auto; */
	flex: 1 500px;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: 500px; */
}
```

# order

생성된 flexbox레이아웃에 각 요소들의 순서를 정할 수 있는 속성이다. 각 요소에 `order`를 준 경우 `order`로 설정한 값이 더 작을 수록 앞부분에 위치한다. 음수로 값을 설정할 수도 있다. 

# align-self

`align-self`는 해당 아이템이 교차축에서 위치하는 곳을 설정하는 속성으로 `align-items`의 작은 버전이라고 볼 수 있다. `align-items`의 값들과 마찬가지로 `stretch`, `flex-start`, `flex-end`, `center`, `baseline`이 값이 될 수 있다.

---

출처

[https://developer.mozilla.org/ko/docs/Learn/CSS/CSS_layout/Flexbox](https://developer.mozilla.org/ko/docs/Learn/CSS/CSS_layout/Flexbox)

[http://www.tcpschool.com/css/css3_expand_flexbox](http://www.tcpschool.com/css/css3_expand_flexbox)

[https://studiomeal.com/archives/197](https://studiomeal.com/archives/197)
