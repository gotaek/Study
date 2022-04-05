
# 가운데 정렬

# 1. position, transform

```css
h1{
	position:absolute;
	left:50%;
	top:50%;
	transform:translate(-50%,-50%)
}
```

부모 엘리먼트를 기준으로 하여 position:absolute를 사용하는 방법이다. left:50%, top:50%로 하니까 왼쪽으로 부터 중간, 위에서부터 중간위치로 이동한다. 그러나 이렇게 하면 적용하는 엘리먼트의 자체 크기가 있기 때문에 살짝 오른쪽 아래에 위치하는 것처럼 보인다. 이를 해결하기 위해 transform: translate(-50%, -50%)를 사용하여 자신의 넓이의 50%만큼 좌측으로, 높이의 50%만큼 위쪽으로 이동시켜 전체적으로 정중앙에 위치하도록한다.

# 2. flex

```css
.flex{
	display:flex;
	justify-content:center;
	align-items:center;
}
```

만약 position:absolute를 사용하기 어려운 상황에서 flex를 사용하기에 유용한데 개인적으로 가장 간편한 방법이라고 생각하기 때문에 가장 많이 사용한다. 

# 3. text-align, line-height

```css
.icon-button{
	height:48px;
	width:48px;
	border-radius:24px;
	text-align:center;
}

.icon-button > span.icon{
	line-height:48px;
}
```

일단 가로로 중앙 정렬을 하기 위해서는 text-align:center를 사용할 수 있다. 또 세로 정렬을 해줘야 하는데 이때는 line-height를 사용해야 한다. text나 폰트기반 아이콘을 중앙에 위치시킬 때 편리하게 사용할 수 있는 방법이다. 정렬하고자 하는 엘리먼트의 line-height를 부모의 height와 같은 값으로 설정하는 것이다. 

# 4. margin: 0 auto 사용하기

```css
body{
	width:100%;
	padding:0;
	margin:0;
}

main{
	width:100%;
	margin:0 auto;
}
```

이 방법은 보통 메인 콘텐츠 컨테이너를 수평 중앙에 둘 때 사용하는 방법이다. 중앙 정렬을 원하는 요소에 margin: 0 auto를 주면서 상하 여백은 없게 하고 좌우로는 여백을 자동적으로 갖게해 중앙 정렬한다. 만약 적용하려는 엘리먼트의 display가 inline이나 inline-block이면 제대로 작동하지 않기 때문에 잘 확인해야 한다. 

# 5. grid, place-content

```css
.container{
	display:grid;
	place-content:center;
}
```

이렇게 grid로 display를 설정하고 중앙정렬을 할 수 있다.

출처

[https://brunch.co.kr/@skykamja24/514](https://brunch.co.kr/@skykamja24/514)
