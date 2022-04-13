# OOCSS

OOCSS(Object Oriented CSS)는 CSS를 모듈 방식으로 코딩하여 중복을 최소화하는 기법이다.

두 가지 원칙은 다음과 같다

1. 구조와 외형의 분리(Separate structure and skin)
2. 컨테이너와 내용의 분리(Separate container and content)

1. **구조와 외형의 분리**

그렇다면 구조와 외형에는 무엇이 있을까?

- 구조: width, height, padding, margin, border
- 외형: color, border-color, font-color, background-color

```css
.button {
  width: 200px;
  height: 50px;
  padding: 10px;
  border: solid 1px #ccc;
  background: linear-gradient(#ccc, #222);
  box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}

.box {
  width: 400px;
  overflow: hidden;
  border: solid 1px #ccc;
  background: linear-gradient(#ccc, #222);
  box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}

.widget {
  width: 500px;
  min-height: 200px;
  overflow: auto;
  border: solid 1px #ccc;
  background: linear-gradient(#ccc, #222);
  box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}
```

이런 식으로 구조를 포함하는 속성들만 모으고, 외형만 포함하는 css속성들을 모은 클래스를 생성한다. 그 후 원하는 요소에 클래스 이름만 달아줌으로 스타일링한다.  이 방식을 사용하여 구조와 외형들을 결합하면 다양한 결과물을 얻을 수 있다.

1. **컨테이너와 내용의 분리**

```css
<!-- Bad --> 
h3 { font-size:16px } 

<!-- Good -->
 .sub-title {font-size:16px}
```

html태그에 직접적으로 스타일링을 하는 것이 아니라 어떤 클래스에 스타일을 지정해 재사용이 가능하도록 하는 것이 가능하다. 

**OOCSS 장점**

- 공통된 부분을 정의해서 재사용이 가능해짐.
- 구조적 상황에 관계없이 동일한 클래스라면 동일한 스타일을 기대할 수 있음.
- 코드의 재사용으로 코드 양이 줄어듬. → CSS파일의 용량의 감소 → 속도 향상

**OOCSS 단점**

- 공통된 클래스가 많기 때문에 수정이 발생할 시 멀티클래스를 사용해야 함.
- 멀티클래스가 많아짐에 따라 유지보수에 어려움
- 코드의 가독성이 떨어짐.

---

**출처 및 참고**

[https://blog.illunex.com/css-방법론-oocss/](https://blog.illunex.com/css-%EB%B0%A9%EB%B2%95%EB%A1%A0-oocss/)

[https://whales.tistory.com/33](https://whales.tistory.com/33)

[https://chlolisher.tistory.com/11](https://chlolisher.tistory.com/11)
