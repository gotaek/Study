# transition

## transition-property

transition-property 프로퍼티는 트랜지션의 대상이 되는 CSS 프로퍼티명을 지정한다. 만약 지정하지 않으면 모든 프로퍼티가 트랜지션의 대상이 된다. 여러개의 프로퍼티를 지정하고 싶다면 쉼표(,)로 구분하여 나열하면 된다. 하지만 모든 CSS프로퍼티가 트랜지션 대상이 되는 것은 아니다. 트랜지션 대상이 될 수 있는 프로퍼티는 다음과 같다.

```css
// Box model
width height max-width max-height min-width min-height
padding margin
border-color border-width border-spacing
// Background
background-color background-position
// 좌표
top left right bottom
// 텍스트
color font-size font-weight letter-spacing line-height
text-indent text-shadow vertical-align word-spacing
// 기타
opacity outline-color outline-offset outline-width
visibility z-index
```

## transition-duration

transition-duration은 트랜지션이 일어나는 시간을 설정하는 것이다. 만약 2s이라고 지정하면 2초동안 서서히 상태가 변화하게 된다. 기본값은 0s이기 때문에 아무런 설정도 하지 않으면 transition이 동작하지 않는다. 만약 transition-property에서 property 들을 여러개 정했다면 transition-duration에서도 쉼표(,)로 구분하여 duration을 지정할 수 있다.

## transition-timing-function

트랜지션 변화 속도를 정할 수 있는 속성이다. linear, ease, ease-in, ease-out, ease-in-out 등이 값으로 설정될 수 있다. animation-timing-function과 비슷한 속성이다. 

## transition-delay

transition이 시작 되기 전의 대기 시간을 설정할 수 있는 속성이다. s과 ms 단위로 값을 설정할 수 있으며 설정 시간 이후에 transition이 실행된다. 만약 2s로 지정했다면 2초 뒤에 변화가 시작되는 것이다. 

## transition

```css
transition: property duration function delay
```

모든 트랜지션의 프로퍼티를 한번에 지정할 수 있는 속성이 transition이다. property, duration, function, delay 순으로 설정한다. 

```css
transition: background 2s ease-in 50ms
```

이런 식으로 설정할 수 있는 것이다.

## transition VS animation 차이

transition속성은 요소의 상태가 변해야 애니메이션을 실행하는 반면 animation 속성은 요소의 모양과 동작을 키프레임 단위로 변경할 수 있다. transition의 경우 hover나 onclick같은 트리거가 있어야 동작한다. 반면 animation은 시작, 정지, 반복까지 제어가 가능하다. 

transition은 css 프로퍼티의 값이 변화할 때, 즉시 변화하는 것이 아니라 일정 시간에 걸쳐서 변화하도록 하는 것이다. 

## 출처
[https://webclub.tistory.com/621](https://webclub.tistory.com/621)
