# 표준 모드와 호환 모드

웹 브라우저는 HTML 문서가 `DOCTYPE`을 가지고 있지 않다면 호환 모드(Quirks mode)로 렌더링한다. 호환 모드로 렌더링을 하게 되면 오래된 웹페이지들을 최신 버전의 브라우저에서도 깨지지 않게 하기 때문에 각 브라우저마다 컨텐츠가 다르게 보일 수 있다. 표준 모드에서는 오래된 브라우저를 모방하여 렌더링 한다. 표준모드(Standard mode)는 브라우저에서 오래되지 않은 문서라고 판단했을 때 사용하는 모드로 W3C표준에 따라 렌더링 한다. 

특별한 경우가 아니라면 HTML5 권장방식에 따라 `<!DOCTYPE html>`을 포함하는 것이 바람직하다.

출처

- [https://a-tothe-z.tistory.com/4](https://a-tothe-z.tistory.com/4)
- [https://github.com/baeharam/Must-Know-About-Frontend/blob/main/Notes/html/standard-quirks.md](https://github.com/baeharam/Must-Know-About-Frontend/blob/main/Notes/html/standard-quirks.md)
