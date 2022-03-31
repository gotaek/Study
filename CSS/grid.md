# Grid

grid를 사용하면 페이지를 행, 열 단위로 편하게 나눌 수 있어서 컨트롤하기에 용이하다. 먼저 grid를 설정하기 위해서는 그리드 컨테이너에 `display:grid`를 설정한다. 그러면 이 안에 있는 요소들은 그리드 아이템들이 된다. 


# 용어 정리

- **그리드 컨테이너 (Grid Container)**display: grid를 적용하는, Grid의 전체 영역입니다. Grid 컨테이너 안의 요소들이 Grid 규칙의 영향을 받아 정렬된다고 생각하면 된다.
- **그리드 아이템 (Grid** **Item)**Grid 컨테이너의 자식 요소들이다.
- **그리드 트랙 (Grid Track)**Grid의 행(Row) 또는 열(Column)
- **그리드 셀 (Grid Cell)**Grid의 한 칸을 가리키는 말이다. <div>같은 실제 html 요소는 그리드 아이템이고, 이런 Grid 아이템 하나가 들어가는 “가상의 칸(틀)”이라고 생각하면 된다.
- **그리드 라인(Grid Line)**Grid 셀을 구분하는 선이다.
- **그리드 번호(Grid Number)**Grid 라인의 각 번호다.
- **그리드 갭(Grid Gap)**Grid 셀 사이의 간격이다.
- **그리드 영역(Grid Area)**Grid 라인으로 둘러싸인 사각형 영역으로, 그리드 셀의 집합이다.

# grid-template-columns, grid-template-rows

그리드를 사용하기 위해서 행의 개수, 열의 개수 그리고 크기를 설정해야하는데 `grid-template-columns`는 열을, `grid-template-rows`는 열을 설정할 수 있는 속성이다. 

```css
grid-template-columns: 200px 200px 200px 200px; 
```

위처럼 설정하면 200px짜리 열이 4개가 된다. 이는 `repeat`를 써서 다음처럼 간편하게 바꿀 수 있다.

```css
grid-template-columns:repeat(4,200px);
```

```css
grid-template-columns: 1fr 1fr 1fr 1fr;
```

fr은 fraction으로 숫자 비율대로 크기를 나눈다.

즉 위의 1fr 1fr 1fr 1fr은 균일하게 1:1:1:1 비율인 3개의 column을 만들겠다는 의미이다.

# minmax, auto-fill, auto-fit

minmax함수는 최솟값과 최댓값을 지정할 수 있는 함수이다. `minmax(100px, auto)`로 설정하면 최소한 높이가 100px이 되고 컨텐츠가 많아지면 자동으로 늘어나게 할 수 있다.

auto-fill을 사용하면 차지할 수 있는 영역에 요소들이 최대한 많이 배치될 수 있도록 한다. repeat(auto-fill, x)로 설정하면 x의 크기를 지키면서 요소들이 최대한 많이 배치되도록 하는 것이다. 따라서 `grid-template-columns:repeat(auto-fill, 100px)`로 하면 100px의 그리드 아이템들이 그리드 컨테이너의 넓이를 가득 채울만큼 행을 만들겠다는 뜻이다. 사실 minmax함수를 함께 사용하여 반응형 페이지를 만드는데 사용하는게 유용하다. 아래처럼 코드를 작성하면 일단 100px의 상자들이 동일한 크기를 가지는 열이 생성된다. 그러나 창의 넓이가 작아지면 각 상자들의 넓이가 1fr을 유지해야 하기 때문에 열의 개수가 줄어든다. 이 때 상자들의 크기도 덩달아 달라지게 된다. 

```css
.grid{
	display:grid;
	grid-template-columns:repeat(auto-fill,minmax(100px,1fr));
	grid-template-rows:100px;
}
```

auto-fit을 사용하면 빈공간이 없도록 요소를 stretch한다. 위의 코드에서 auto-fill을 auto-fit으로 변경하면 창의 크기가 줄어들어도 1fr을 유지하려고 한다. 

`auto-fill`, `auto-fit`, `minmax` 를 조합한다면 반응형으로 grid 레이아웃을 만들기에 좋을 것이다.

# row-gap, column-gap

간단하게 행과 열의 간격을 조정할 수 있는 속성이다. 

```css
.parent{
	column-gap:10px;	
	row-gap:10px;
}
```

# grid-auto-columns, grid-auto-rows

만약 그리드의 행을 2개, 열을 2개로 설정했다고 하자. 따라서 그리드 셀이 총 4개인데 그리드 아이템이 6개라고 하자. 4개가 배치되고 남은 2개는 어디에 배치될까? 원하지 않는 레이아웃으로 이상한 곳에 원하지 않는 크기로 배치될 것이다. 이럴 때 사용할 수 있는 속성이 `grid-auto-columns`, `grid-auto-rows`, `grid-auto-flow`이다. 

미리 몇개가 들어갈 지 모르는 경우 이 속성들을 사용한다. 먼저 `grid-auto-flow`는 배치되어야 할 공간이 지정되지 않은 나머지 그리드 아이템들이 붙여질 방향을 설정한다. `grid-auto-flow: column`은 행을 추가하여 배치하는 것이고, `grid-auto-flow:row`는 열을 추가하여 배치하는 것이다. grid-auto-flow 설정을 한 값에 따라 `grid-auto-columns`나 `grid-auto-rows`를 사용하면 되겠다. 두 개의 속성은 추가된 행이나 열의 크기를 지정하는 속성이다. 

```css
.grid{
	display:grid;
	grid-template-columns:repeat(4,1fr);
	grid-template-rows:100px;
	grid-auto-rows:100vh; 
	grid-auto-flow:row;
} 
```

# 각 셀의 영역 지정

각 셀의 영역 지정은 같은 레이아웃을 세가지 방법으로 지정하는 예시를 통해 알아보자

## grid-template-areas, grid-area

각 영역(Grid Area)에 이름을 붙이고, 그 이름을 이용해서 배치하는 방법이다. 

각 영역에서는 `grid-area`를 이용해서 이름을 붙인다음에 그리드 컨테이너에서 `grid-template-areas`에 붙인 이름을 적어주는 방식으로 배치한다.

```css
.father{
	display:grid;
	grid-template-columns:repeat(4,200px); /*200px 200px 200px 200px와 동일*/
	grid-template-rows:100px repeat(2,200px) 100px;
	grid-template-areas:
	"header header header header"
	"content content content nav"
	"content content content nav"
	"footer footer footer footer";
	column-gap:10px;
	row-gap:10px;
}
.header { grid-area: header; }
.content { grid-area: content; }
.nav { grid-area: nav; }
.footer { grid-area: footer; }
```

## grid-template

```css
.parent {
  display: grid;
  grid-template:
    "header header header header" 100px
    "content content content nav" 400px
    "footer footer footer footer" 100px; / 200px 200px 200px 200px
}
.header {
  grid-area: header;
}
.content {
  grid-area: content;
}
.nav {
  grid-area: nav;
}
.footer {
  grid-area: footer;
}
```

`grid-template-areas`를 사용하는 것처럼 문자열을 입력하고 행의 크기를 지정한다. 그리고 가장 맨뒤에는 / 를 적어 구분하고 각 열의 크기를 지정한다.

## gird-column, grid-row

```css
.parent {
  display: grid;
  grid-template-columns: repeat(4, 200px); /*200px 200px 200px 200px와 동일*/
  grid-template-rows: 100px repeat(2, 200px) 100px;
}
.header {
  grid-column-start: 1;
  grid-column-end: 5;
  /*grid-column:1/5;(다음과 같이 단축 가능)*/
  /*grid-colum:1/-1;(-1로 마지막 줄을 대체 가능)*/
  /*grid-column:span 4;(cell의 갯수를 명시)*/
  /*gird-column:1/span 4;(시작점을 명시할 수도 있음)*/
}
.content {
  grid-column-start: 1;
  grid-column-end: 4;
  grid-row-start: 2;
  grid-row-end: 4;
}
.nav {
  grid-row-start: 2;
  grid-row-end: 4;
}
.footer {
  grid-column: 1/5;
  grid-row: 4/5;
}
```

`grid-column-start`, `grid-column-end`, `grid-row-start`, `grid-row-end`를 사용해 각 요소들이 위치해아 하는 공간을 그리드 번호로 지정한다.
