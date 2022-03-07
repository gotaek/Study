# DOCTYPE

문서형식선언(Document Type Declaration) 또는 DOCTYPE이란 어떤 SGML이나 XML 기반 문서 내에 그 문서가 특정 문서 형식 정의(DTD)를 지정하는 것이다. 웹 브라우저가 예상해야 하는 문서 형식을 지정하는 것과 같다.

DTD(Document Type Definition)는 문서 형식을 정의하는 컴퓨터 용어로 SGML 계열의 마크업 언어에서 문서 형식을 정의하는 것이다.

HTML 5 이전의 버전들은 SGML을 기반으로 만들어졌기 때문에 DTD를 상세하게 정의해야 한다. HTML 5부터는 SGML에 기반을 두지 않기 때문에 `<!DOCTYPE html>` 이렇게만 문서의 가장 첫 줄에 명시함으로 문서 형식을 간단하게 선언할 수 있다. 만약 이렇게 명시하지 않는다면 호환모드(quirks mode)로 동작한다. 호환 모드에서는 각 브라우저마다 저마다의 방식으로 렌더링하기 때문에 크로스 브라우징 이슈가 심해진다.

출처: [https://github.com/baeharam/Must-Know-About-Frontend/blob/main/Notes/html/doctype.md](https://github.com/baeharam/Must-Know-About-Frontend/blob/main/Notes/html/doctype.md)
