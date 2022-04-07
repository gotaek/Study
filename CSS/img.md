# img vs background-image

HTML에는 img태그가 있고 CSS에는 background-image라는 속성이 있다. 두 개의 기술 모두 이미지를 웹페이지에 넣는 방식이다. 두 가지는 어떤 차이가 있고, 언제 사용하는게 좋을까?

```html
<img src="이미지 경로" alt="이미지 설명">
```

```css
background-image: url("이미지 경로");
```

일단 두개는 다음과 같은 방식으로 사용한다 위에서도 차이를 쉽게 확인할 수 있듯이 img태그에서는 alt 속성을 사용해 이미지 설명을 줄 수 있지만 background-image에서는 따로 이미지 설명 텍스트를 지정할 수는 없다. 이는 SEO와 접근성 측면에서 중요한 역할을 한다. alt속성이나 title속성은 search engine이 인덱싱할 수 있게하는 동시에 스크린 리더에서 읽히기 때문에 img태그를 사용한다면 alt나 title를 사용하는 것이 좋겠다. 

또 img에서는 하나의 이미지만 삽입할 수 있지만 background-image에서는 쌓임 맥락에 따라 여러개의 이미지를 겹쳐서 위치시킬 수 있다. 

이미지가 단지 디자인적인 역할을 하지 않고, 컨텐츠와 밀접하게 연관되어 있을 때는 img태그를 사용한다. 반면에 단순히 컨텐츠와 연관되지 않고 그 자체로 디자인 요소일 경우에는 background-image를 사용한다. 

성능 측면에서는 html태그가 css속성보다 더 좋다. 큰 사이즈의 이미지를 background-image를 통해 가져오기 위해서는 꽤 오랜 시간이 걸리지만 img태그는 상대적으로 더 빠르다. 그러나 css sprite 기법과 background-image를 결합하여 함께 사용한다면 이미지 수정, 보관등에 용이하고 로딩 속도도 더 빨라지게 된다.

---
출처

[https://www.oodlestechnologies.com/blogs/difference-between-html-img-tag-and-css-background-image/](https://www.oodlestechnologies.com/blogs/difference-between-html-img-tag-and-css-background-image/)

[https://chlolisher.tistory.com/77](https://chlolisher.tistory.com/77)

[https://developer.mozilla.org/ko/docs/Web/CSS/background-image](https://developer.mozilla.org/ko/docs/Web/CSS/background-image)

[https://developer.mozilla.org/ko/docs/Web/HTML/Element/img](https://developer.mozilla.org/ko/docs/Web/HTML/Element/img)
