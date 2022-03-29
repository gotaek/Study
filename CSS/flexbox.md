# Flexbox

오랫동안 웹 페이지 레이아웃을 float, inline-block등을 사용해서 잡아왔지만 flexbox가 나오면서 그 방법들을 사용할 이유들이 사라졌다.

- 부모 요소 내부에 포함된 블록 콘텐츠를 세로로 중심부에 맞추기.
- 사용 가능한 너비와 높이에 관계없이 하나의 컨테이너에 포함된 모든 자녀 요소가 주어진 너비와 높이를 똑같은 크기로 점유하기.
- 다단 레이아웃에 포함된 모든 단이 서로 다른 크기의 콘텐츠를 포함하고 있더라도 동일한 높이로 채택하기.

즉 쉽게 레이아웃을 설정하는데 도움을 주는 것이 flexbox이다.

# main-axis & cross-axis

먼저 flexbox를 사용하기 위해서는 어떤 요소에 display: flex로 설정해야 한다. 기본 축 (main-axis)는 가로 방향으로 웹 페이지를 가로지르는 축이다. 그리고 교차 축(cross-axis)는 기본 축에 수직이 되는 방향의 축이다. 이는 기본적으로 설정되는 값으로 만약 flex-direction을 변경하면 반대가 된다. 

우선 기본적으로 flex-direction은 row이다. 이때의 축 방향은 위의 설명과 같다. 그러나 flex-direction:column으로 하면 기본 축이 세로 방향이 되고, 교차 축이 가로 방향이 된다. 

# justify-content

justify-content는 기본 축에서 flex item들을 어떻게 배치할 지를 정한다. justify-content에는 다음과 같은 값을 가질 수 있다.

1. flex-start : 기본 설정으로, 플렉스 요소는 플렉스 컨테이너의 앞쪽에서부터 배치됩니다.
2. flex-end : 플렉스 요소는 플렉스 컨테이너의 뒤쪽에서부터 배치됩니다.
3. center : 플렉스 요소는 플렉스 컨테이너의 가운데에서부터 배치됩니다.
4. space-between : 플렉스 요소는 요소들 사이에만 여유 공간을 두고 배치됩니다.
5. space-around : 플렉스 요소는 앞, 뒤, 그리고 요소들 사이에도 모두 여유 공간을 두고 배치됩니다.
6. space-evenly: 플렉스 요소 앞, 뒤, 그리고 요소들 사이에서 모두 여유 공간을 두고 배치되지만 모두 같은 간격을 가진다.


# align-items

align-items는 교차 축에서 flex item들을 어떻게 배치할 지를 정한다. 만약 flex-direction이 변경되면 당연히 메인 축과 교차 축도 다르기 때문에 아래의 속성 값들도 축에 따라 다르게 나타난다.

1. stretch: 아이템들이 수직축 방향으로 끝까지 쭈욱 늘어납니다.
2. flex-start: 아이템들을 시작점으로 정렬합니다.flex-direction이 row(가로 배치)일 때는 위, column(세로 배치)일 때는 왼쪽이에요.
3. flex-end: 아이템들을 끝으로 정렬합니다.flex-direction이 row(가로 배치)일 때는 아래, column(세로 배치)일 때는 오른쪽이에요.
4. center: 아이템들을 가운데로 정렬합니다.
5. baseline: 아이템들을 텍스트 베이스라인 기준으로 정렬합니다.

# flex-wrap

flex 요소를 담고 있는 컨테이너의 크기가 변경될 때 그 안의 flex요소들을 어떻게 배치할 지에 대한 것으로 반응형 웹페이지를 만들 때 중요한 역할을 한다.

속성 값으로는 no-wrap, wrap, wrap-reverse가 있다. no-wrap은 컨테이너의 크기가 줄어들어도 flex요소의 줄바꿈이 일어나지 않고 컨테이너의 넓이를 넘어서서 배치된다. wrap은 만약 flex요소가 배치될 공간이 없으면 다음 줄에 배치된다. wrap-reverse는 flex요소가 배치될 공간이 없을 시 아래줄에 배치되는 것이 아니라 위에 배치된다.

# flex-flow

flex-direction과 flex-wrap을 한꺼번에 지정할 수 있는 단축 속성이다. 반응형으로 웹페이지를 제작할 일이 많을 터이니 다음과 같이 사용하도록 하자.

```css
flex-flow: row wrap;
```

# align-content

flex-wrap:wrap으로 설정해서 flex요소들이 두줄에 걸쳐 나올 때 사용하면 좋을 속성이다.  justify-content에서 space-between, space-around, space-evenly 등의 값이 메인 축에 있는 flex요소들의 간격들을 조정해주는 것이었다면 align-content는 두줄 이상으로 flex 요소가 되었을 때 그 줄 들의 간격을 조정하는 것이다. 다음과 같은 속성값들을 가질 수 있다.

1. stretch : 기본 설정으로, 플렉스 라인의 높이가 남는 공간을 전부 차지하게 됩니다.
2. flex-start : 플렉스 라인은 플렉스 컨테이너의 앞쪽에 뭉치게 됩니다.
3. flex-end : 플렉스 라인은 플렉스 컨테이너의 뒤쪽에 뭉치게 됩니다.
4. center : 플렉스 라인은 플렉스 컨테이너의 가운데에 뭉치게 됩니다.
5. space-between : 플렉스 라인은 플렉스 컨테이너에 고르게 분포됩니다.
6. space-around : 플렉스 라인은 플렉스 컨테이너에 고르게 분포됩니다. 단, 양쪽 끝에 약간의 공간을 남겨둡니다.
7. space-evenly: 플렉스 요소 앞, 뒤, 그리고 요소들 사이에서 모두 여유 공간을 두고 배치되지만 모두 같은 간격을 가진다.

---

출처

[https://developer.mozilla.org/ko/docs/Learn/CSS/CSS_layout/Flexbox](https://developer.mozilla.org/ko/docs/Learn/CSS/CSS_layout/Flexbox)

[http://www.tcpschool.com/css/css3_expand_flexbox](http://www.tcpschool.com/css/css3_expand_flexbox)

[https://studiomeal.com/archives/197](https://studiomeal.com/archives/197)
