# absolute, translate

 `transform`속성은 요소에 회전, 크기 조절, 기울이기, 이동 효과를 부여할 수 있다. 그 중 translate는 수평, 수직, 그리고 3차원 Z축까지 요소를 이동 시켜주는 것이다.

## **Absolute positioning & translate 비교**

**1. 목적**

- absolute : 포지셔닝 (특정 위치에 위치시키기 위함)
- translate : 디자인 모션

**2. x축,y축 시작점**

- absolute : 조상 엘리먼트의 최상단좌측이 시작점이자 기준점이 됩니다.
- translate : 부모 요소에서 따로 지정해주는 것이 아니라면 요소가 갖고있는 최상단좌측이 기준점이자 시작점이 됩니다.

**3. 영향력**

- absolute : 주변 요소에 영향이 있다.
- translate : 좌표 공간을 변형시키기에 다른 요소(형제 등등..)에 영향을 미치지 않는다.

**4. 성능**

- absolute : **CPU 처리** (reflow나 repaint 발생)
- translate : **GPU 처리**

만약 webkit 브라우저에서 가운데로 정렬하기 위해

```css
position:absolute;
left:50%;
top:50%;
transform:translate(-50%,-50%);
```

이렇게 사용할때 텍스트 또는 사진이 흐릿하게,, 뿌옇게 보이는 버그가 발생한다.

---
출처

[https://bbosong-develop.tistory.com/5](https://bbosong-develop.tistory.com/5)
