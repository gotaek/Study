# clearing

float속성을 설정하다 보면 부모가 float된 자식을 못담아내는 경우를 확인하거나 float다음 요소가 float의 영향을 받는 현상을 자주 목격하게 된다. float된 요소의 높이를 부모가 인식하지 못하기 때문에 부모가 자식을 담아낼 수 없던 것이다. 따라서 float를 해제해주어야 한다. float된 요소의 float를 해제하는 것이 아닌 float요소 주변의 블록들이 float의 영향을 벗어나게 하는 것, 그것이 바로 클리어링이다. 

## clear

우선 clear라는 속성에 대해서 알아보자. clear 속성은 float된 엘리먼트에 사용하는 것이 아니라 float된 요소의 주면 엘리먼트들이 사용하는 것이다. left 값은 왼쪽에 float된 요소가 존재하지 않도록 하는 것이다. 따라서 clear:left를 사용하면 해당 요소가 float된 요소 오른쪽에 위치하는 것이 아니라 아래쪽에 위치한다. clear:right도 마찬가지로 float된 요소가 오른쪽에 존재하지 않도록 하는 것이다. clear:both는 왼쪽, 오른쪽 모두 float된 요소가 지정해제 되도록 한다. 

## 1. float를 부모에게도

float를 해제하는 방법 중 가장 단순한 방법은 부모에게도 float 속성을 주는 것이다. 이 방법을 사용하면 부모가 자식의 높이를 인식하게 할 수는 있지만 float 속성이 겹겹이 설정되어 있는 경우 조상 엘리먼트 모두에게 float 속성을 적용해야 하기 때문에 그리 좋은 방법은 아니다. 

## 2. overflow 값을 변경

이번에도 역시 부모 요소에게 적용하는 것인데 부모의 overflow를 hidden 또는 auto로 설정하는 것이다. 보통 overflow는 넘치는 것을 숨길 때 사용하는 속성인데 float와 함께 사용하면 넘치는 내용을 부모요소가 포함시켜 숨긴다는 것으로 볼 수 있다. 자식의 높이가 부모보다 크다면 auto로 설정했을 때 스크롤바가 생성되고, hidden인 경우에는 내용이 잘릴 수 있기 때문에 이 역시도 많이 사용하는 방법은 아니다. 

## 3. 빈 블록 생성

float된 요소의 마지막에 내용이 없는 빈 블록을 생성하는 것도 하나의 방법이 될 수 있다. 이 블록에 clear:both 속성을 주게 되면 부모가 자식의 높이를 인식할 수 있게 된다. 그러나 아무런 내용이 없는 블록을 만드는 것도 좋은 방법이 아니다. 

## 4. 가상선택자

float엘리먼트의 부모엘리먼트에 :after라는 가상요소를 사용해서 HTML문서에 존재하지 않는 새로운 요소를 생성한다. 그 요소에 clear속성을 주어 float를 해제한다. 이 방식을 사용하면 빈 블록을 생성하지 않고 쉽게 해결할 수 있다. 

```css
.parent:after {
	content: ""; 
	display:block;
	clear:both; 
}
```

보통 clearfix라는 클래스이름을 사용해 float해제가 필요할 때마다 float요소가 포함된 부모 요소에 clearfix클래스를 달아주면서 문제를 해결한다. 

```css
.clearfix:before,
.clearfix:after {
    content: " "; /* 1 */
    display: table; /* 2 */
}
 
.clearfix:after {
    clear: both;
}
```

---

출처

[https://naradesign.github.io/float-clearing.html](https://naradesign.github.io/float-clearing.html)

[https://webclub.tistory.com/606](https://webclub.tistory.com/606)
