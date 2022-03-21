# 마진 겹침 현상(Margin-Collapsing)

마진 겹침 현상(Margin Collapsing)은 block 모델에서 margin이 겹치는 현상을 말한다. 두 개 이상의 블록이 위 아래로 위치할 때 블록의 각 margin이 더해지는 것이 아니라 더 큰 margin으로 겹쳐지는 현상이다. 마진 겹침 현상은 block모델에 한해서만 적용되는 것이기 때문에 display가 inline, inline-block인 경우에는 발생하지 않는다. 좌우로는 margin이 상쇄되지 않는다.

## 마진 겹침 현상이 일어나는 상황

1. 인접한 박스의 상하 margin이 겹치는 상황
2. 부모 자식간의 margin이 겹치는 상황
3. 빈 요소의 상하 margin이 겹치는 상황

## 마진 상쇄 규칙 예외

다음과 같은 상황에서는 인접 요소 간 마진 상쇄가 일어나지 않는다.

- 박스가 `position: absolute` 된 상태
- 박스가 `float: left/right` 된 상태 (단, clear 되지 않은 상태)
- 박스가 `display: flex` 일 때 내부 flexbox item
- 박스가 `display: grid` 일 때 내부 grid item

따라서 마진 겹침 현상을 해결하기 위해서 inline-block을 사용하거나 부모 자식 간의 문제에서는 부모, 자식 모두에게 border나 padding 옵션을 주어야 한다. 또 float 옵션을 주는 방법과 position을 absolute로 설정하는 방법도 존재한다. 

---
#### 출처

[https://velog.io/@raram2/CSS-마진-상쇄Margin-collapsing-원리-완벽-이해](https://velog.io/@raram2/CSS-%EB%A7%88%EC%A7%84-%EC%83%81%EC%87%84Margin-collapsing-%EC%9B%90%EB%A6%AC-%EC%99%84%EB%B2%BD-%EC%9D%B4%ED%95%B4)
