# BFC

> **블록 서식 맥락**
(block format context)은 웹 페이지를 렌더링하는 시각적 CSS의 일부로서, 블록 박스의 레이아웃이 발생하는 지점과 플로팅 요소의 상호작용 범위를 결정하는 범위입니다.
> 

MDN은 다음과 같이 설명되어 있는데 이해하기가 어려워서 다른 블로그를 찾아 개념을 확인했다. 

요소에 새로운 블록 양식화 문맥(이하 BFC)을 적용하면 하위 요소를 대상으로 한 독립적인 레이아웃 환경을 만들수 있고 다른 주변 요소와도 레이아웃 관계를 형성할 수 있다.

블록 서식 맥락은 다음과 같은 경우에 생성됩니다.

- 문서의 루트 요소(`[<html>](https://developer.mozilla.org/ko/docs/Web/HTML/Element/html)`).
- 플로팅 요소(`[float](https://developer.mozilla.org/ko/docs/Web/CSS/float)`이 `none`이 아님).
- 절대 위치를 지정한 요소(`[position](https://developer.mozilla.org/ko/docs/Web/CSS/position)`이 `absolute` 또는 `fixed`).
- 인라인 블록(`[display](https://developer.mozilla.org/ko/docs/Web/CSS/display)`가 `inline-block`).
- 표 칸(`[display](https://developer.mozilla.org/ko/docs/Web/CSS/display)`가 `table-cell`, HTML 표 칸의 기본값).
- 표 주석(`[display](https://developer.mozilla.org/ko/docs/Web/CSS/display)`가 `table-caption`, HTML 표 주석의 기본값).
- `[display](https://developer.mozilla.org/ko/docs/Web/CSS/display)`가 `table`, `table-row`, `table-row-group`, `table-header-group`, `table-footer-group` (HTML 표에서, 각각 표 전체, 행, 본문, 헤더, 푸터의 기본값) 또는 `inline-table`인 요소가 암시적으로 생성한 무명 칸.
- `[overflow](https://developer.mozilla.org/ko/docs/Web/CSS/overflow)`가 `visible`이 아닌 블록 요소.
- `[display](https://developer.mozilla.org/ko/docs/Web/CSS/display)`가 `flow-root`.
- `[contain](https://developer.mozilla.org/ko/docs/Web/CSS/contain)`이 `layout`, `content`, `paint`.
- 스스로 플렉스, 그리드, 테이블 컨테이너가 아닌 경우의 플렉스 항목(`[display](https://developer.mozilla.org/ko/docs/Web/CSS/display)`가 `flex` 또는 `inline-flex`인 요소의 바로 아래 자식)
- 스스로 플렉스, 그리드, 테이블 컨테이너가 아닌 경우의 그리드 항목(`[display](https://developer.mozilla.org/ko/docs/Web/CSS/display)`가 `grid` 또는 `inline-grid`인 요소의 바로 아래 자식)
- 다열 컨테이너(`[column-count` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/column-count) 또는 (`[column-width` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/column-width)가 `auto`가 아닌 경우. `column-count: 1` 포함).
- `[column-span` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/column-span)이 `all`인 경우. 해당하는 요소가 다열 컨테이너 안에 위치하지 않아도 항상 새로운 블록 서식 맥락을 생성해야 합니다. ([명세 변경](https://github.com/w3c/csswg-drafts/commit/a8634b96900279916bd6c505fda88dda71d8ec51), [Chrome 버그](https://bugs.chromium.org/p/chromium/issues/detail?id=709362))

BFC는 요소를 BFC로 생성하면 모든 것이 그 안에 포함되기 때문에 페이지 내부의 작은 레이아웃이라고 할 수 있다. 

사실 BFC의 정의 자체를 이해하는 것보다 어느 상황에서 사용해야 하는 지 이해하는 것이 더욱 빠를 것 같다. 의도한 것과 다르게 배치되는 레이아웃을 올바르게 잡는 방법이라고 생각하면 된다. 

블록 서식 맥락은 레이아웃에 영향을 주지만, 보통 맥락을 생성하는 요소는 아래와 같은 작용을 하기 때문에 위치 설정과 플로팅 해제를 위해 더 많이 사용한다.

- 내부 플로팅 가두기 (float된 요소 포함하기)
- float된 요소를 글자들이 감싸는 것을 방지
- [여백 상쇄](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing) 제거 (마진 겹침 현상 제거)

float 해제를 할 때 가장 많이 사용되는 clearfix를 하는 방법도 있었다. 그러나 다른 방법으로는 부모 요소에 overflow:hidden을 설정하거나 부모 요소에 float를 설정하는 방법, 부모요소의 display를 inline-block으로 하는 것이 있었다. 이 방법들은 모두 BFC를 적용한 것이기 때문에 가능한 것이었다. 

마진 겹침 현상은 같은 BFC에 놓여있을 경우에 나타난다. 따라서 새로운 블록을 생성하 다른 BFC를 적용한다면 마진 겹침 현상을 해결할 수 있다. 부모 태그에 overflow를 auto로 설정하는 방법으로 부모 요소와 자식 요소간의 마진 겹침현상은 해결할 수 있지만 형제관계에 있는 자식 요소는 여전히 마진 겹침 현상이 발생한다. 따라서 자식 요소 각각에 다른 BFC를 적용한다면 자식들 사이에서도 마진 겹침 현상을 제거할 수 있다. 

그러나 BFC를 적용할 때 부작용이 있을 수 있으니 상황에 맞게 잘 적용하는 것이 중요하다.

- `display: table` may create problems in responsiveness
- `overflow: scroll` may show unwanted scrollbars
- `float: left` will push the element to the left, with other elements wrapping around it
- `overflow: hidden` will clip elements that overflow

---
출처
[https://doodreamcode.tistory.com/203](https://doodreamcode.tistory.com/203)

[https://www.smashingmagazine.com/2017/12/understanding-css-layout-block-formatting-context/](https://www.smashingmagazine.com/2017/12/understanding-css-layout-block-formatting-context/)

[https://medium.com/@ritz078/block-formatting-contexts-in-css-3a9555355019](https://medium.com/@ritz078/block-formatting-contexts-in-css-3a9555355019)

[https://developer.mozilla.org/ko/docs/Web/Guide/CSS/Block_formatting_context](https://developer.mozilla.org/ko/docs/Web/Guide/CSS/Block_formatting_context)
