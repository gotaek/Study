# 점진적 향상, 우아한 성능 저하

점진적 향상(Progressive Enhancement)과 우아한 성능 저하(Graceful Degradation)는 웹 접근성을 위해 웹을 디자인하는 방식이다. 점진적 향상과 우아한 성능 저하 모두 아래의 핵심을 가진다.

> - 모든 브라우저에 대하여 웹 페이지의 필수 콘텐츠 및 기능을 제공할 수 있어야 한다.
> - 더 향상된 브라우저, 디바이스를 가진 사람들에게 웹 페이지의 향상된 버전을 제공한다.

## 점진적 향상 (Progressive Enhancement)

점진적 향상은 레이어를 하나씩 쌓아 올리면서 단순한 것부터 복잡한 것까지 동작하도록 발전시키는 방법이다. 가장 기본적인 것은 HTML, CSS, JavaScript로 레이어를 나누어서 차례대로 구현하는 것이다. HTML로 구조(Structure)를 구성하고, CSS를 사용해 표현(Presentation)한 후 JavaScript로 동적인 행위(Behavior)를 하도록 한다. 낮은 수준의 디바이스, 브라우저를 가진 클라이언트를 위한 응용 프로그램을 지원하는 동시에 더 향상된 버전의 브라우저를 가진 클라이언트에게는 기능을 강화한 응용 프로그램을 지원하는 방법인 것이다.

### 특징

점진적 향상 방법에서는 계층형으로 발전시키기 때문에 하나의 계층에서는 문제가 거의 없다. 따라서 추가된 기능을 지원할 때에 최소한 이전 계층들에 대해서는 신뢰할 수 있다는 장점을 가진다. 기존의 구형 디바이스와 브라우저에 대한 문제를 방지할 수 있는 것이다. 또한 점진적 향상은 사용자와 크롤러 모두에게 좋은 접근성을 제공한다. 그러나 복잡한 인터페이스를 구현해야 하는 경우에는 어쩔 수 없이 상응하는 복잡한 기술을 사용해야 하기 때문에 점진적 향상 기반으로 구축하기 어려울 수 있다.

## 우아한 성능 저하 (Graceful Degradation)

우아한 성능 저하는 점진적 향상과 정반대의 성격을 가진다. 최신 기술을 사용하여 최신 버전의 브라우저, 디바이스에 맞도록 기능을 구현한 후에 오래된 버전의 브라우저, 디바이스에서도 비슷하게 작동되도록 구현하는 것이다. 우아한 성능 저하는 모든 사람에게 최상의 경험을 제공하는 것이 아니라 최신 버전의 브라우저를 위한 솔루션을 개발하는 것이 목표이다. 오래된 버전을 사용하고 있는 사용자가 많이 있지 않을 뿐더러 최신 버전과 큰 차이를 느끼지 못할 만큼 오래된 버전에도 필수적인 기능은 제공하기 때문이다. 또한 모바일 최적화에도 우아한 성능이라는 개념이 사용되는데 우선 데스크 탑을 기준으로 웹 사이트를 제작한 다음 모바일에서도 지원 가능하도록 기능과 디자인을 단계적으로 조절하는 것도 우아한 성능 저하의 원칙을 적용한 것이다.

### 특징

오래된 버전의 기기와 브라우저에서도 새로운 기능이 있는 웹페이지를 제공하기 때문에 사용자는 기기와 브라우저에 상관없이 비슷하게 컨텐츠를 제공받을 수 있다. 이미지들이 많이 없는 웹사이트에서는 해당 방법이 좋은 솔루션이 될 수 있지만 이미지, 비디오, 라이브 채팅 등 다양한 기능들이 많이 포함되어 있는 경우에는 브라우저마다 큰 차이가 발생할 수 있기 때문에 우아한 성능 저하를 사용하기에는 적합하지 않다.

---
#### 출처 및 참고

+ [https://intellegibilisverum.tistory.com/entry/점진적-기능-향상](https://intellegibilisverum.tistory.com/entry/%EC%A0%90%EC%A7%84%EC%A0%81-%EA%B8%B0%EB%8A%A5-%ED%96%A5%EC%83%81)

+ [https://medium.com/the-mighty-programmer/what-is-progressive-enhancement-and-why-it-matters-e80c7aaf834a](https://medium.com/the-mighty-programmer/what-is-progressive-enhancement-and-why-it-matters-e80c7aaf834a)

+ [https://www.seobility.net/en/wiki/Progressive_Enhancement](https://www.seobility.net/en/wiki/Progressive_Enhancement)

+ [https://www.seobility.net/en/wiki/Graceful_Degradation](https://www.seobility.net/en/wiki/Graceful_Degradation)
