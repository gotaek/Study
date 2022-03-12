# srcset

반응형 웹페이지란 최근에는 없어서는 안될만큼 중요한 부분이다. 반응형 웹페이지는 디스플레이의 뷰포트에 따라 웹 디자인이 변경되는 웹 페이지이다. 유저에게 좋은 인터페이스를 제공하는 동시에 다양한 디바이스에서 접근하는 것을 가능하게 하기 때문에 최근 대부분의 웹페이지는 반응형 웹페이지로 이루어져 있다. 

노트북으로 보던 웹페이지의 이미지가 모바일 환경에서도 동일하게 같은 사이즈로 다운받아져야 할 이유가 있을까? 작은 모바일 환경일수록 커다란 이미지는 필요없다. 반응형 이미지를 사용하면 디바이스의 뷰포트에 따라 크기가 다른 이미지를 제공할 수 있다. `<img>`태그의 `srcset`속성을 사용한다. 

```html
<img srcset="test-3202.jpg 320w,
             test-480w.jpg 480w,
             test-800w.jpg 800w"
     sizes="(max-width: 320px) 280px,
            (max-width: 480px) 440px,
            800px"
     src="test-800w.jpg" alt="testing img">
```

`srcset`에는 사용할 이미지를 쉼표를 기준으로 나열한다. 쉼표로 구분되어 있는 문자열에는 공백이 포함되어 있는 것을 확인할 수 있는데 이미지 파일명과 이미지의 사이즈를 공백을 삽입하여 나타낸 것이다. 

`sizes` 속성에는 뷰포트에 따라 어떤 이미지가 최적인지를 나타낸다. 미디어 조건문과 이미지가 채울 슬롯의 너비를 공백을 활용해 나타낸 것이고, 나열할 수 있다. 

출처

- [https://developer.mozilla.org/ko/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images](https://developer.mozilla.org/ko/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)
- [https://velog.io/@heumheum2/srcset-sizes](https://velog.io/@heumheum2/srcset-sizes)
