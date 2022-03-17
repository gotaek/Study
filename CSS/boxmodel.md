# Box 모델

모든 HTML요소는 box모델로 이루어져 있어서 패딩(padding), 테두리(border), 마진(margin), 그리고 내용(content)로 구성되어 있다. 

1. 내용(content) : 텍스트나 이미지가 들어있는 박스의 실질적인 내용 부분이다.
2. 패딩(padding) : 내용과 테두리 사이의 간격입니다. 패딩은 눈에 보이지 않는다.
3. 테두리(border) : 내용과 패딩 주변을 감싸는 테두리이다.
4. 마진(margin) : 테두리와 이웃하는 요소 사이의 간격이며 눈에 보이지 않는다.

![http://www.tcpschool.com/lectures/img_css_boxsize.png](http://www.tcpschool.com/lectures/img_css_boxsize.png)

CSS에서 height와 width를 설정할 때는 content부분만을 대상으로 한다. 즉 패딩, 테두리, 마진 등은 width 설정에 포함되지 않는다.
