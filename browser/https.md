# HTTPS

HTTP는 기본적으로 클라이언트와 서버사이에서 데이터를 주고받는 통신 프로토콜이다. 그러나 HTTP에는 단점이 존재했는데 주고 받는 데이터가 전송될 때 암호화되지 않기 때문에 보안에 취약하다는 것이었다. 이러한 문제를 해결하기 위해 중요한 정보를 주고 받을 때 도난당하는 것을 막게 하는 프로토콜이 생성되었다. 이를 HTTPS라고 한다. 기존의 HTTP를 암호화한 버전이 HTTPS가 된 것이다. SSL(Secure Socket Layer)라는 프로토콜을 사용해 주고 받는 정보를 암호화한다. 이후 SSL은 TLS (Transport Layer Security)로 발전되어 현재는 SSL/TLS라는 단어를 혼용해서 사용하고 있다.

 

- **공개키(Public Key)와 비밀키(Private Key)** : 공개키는 모두가 볼 수 있는 키이며 비밀키는 소유자만이 가지고 있는 키로 암/복호화에 사용된다.
- **대칭키 암호화** : 서버와 클라이언트가 암호화/복호화에 동일한 비밀키를 사용하는 방식, 키를 공유하는데 어려움이 있으나 속도가 빠르다.
- **비대칭키 암호화** : 서버와 클라이언트가 암호화/복호화에 각각 다른 비밀키를 사용하는 방식, 공개키를 통해서 암호화를 하고 비밀키를 통해서 복호화를 한다. 공개키는 공개해도 상관없으니 키 관리에 어려움이 없으나, 속도가 느리다.
- **인증기관(Certificate Authority, CA)** : 클라이언트가 접속을 요청한 서버가 의도한 서버가 맞는지 인증해주는 역할을 하는 보증된 기업들이다. 클라이언트는 서버에 요청을 해서 CA가 발급한 인증서를 받은 뒤 CA의 공개키로 복호화하여 신뢰할 만한 인증서인지 검증한다. CA의 공개키로 복호화되는 암호화는 오직 CA의 비밀키로 암호화한 경우밖에 없기 때문에 복호화되면 신뢰할 만한 것이다.

---

출처

- [https://blog.wishket.com/http-vs-https-차이-알면-사이트의-레벨이-보인다/](https://blog.wishket.com/http-vs-https-%EC%B0%A8%EC%9D%B4-%EC%95%8C%EB%A9%B4-%EC%82%AC%EC%9D%B4%ED%8A%B8%EC%9D%98-%EB%A0%88%EB%B2%A8%EC%9D%B4-%EB%B3%B4%EC%9D%B8%EB%8B%A4/)
- [https://github.com/baeharam/Must-Know-About-Frontend/blob/main/Notes/network/https.md](https://github.com/baeharam/Must-Know-About-Frontend/blob/main/Notes/network/https.md)
