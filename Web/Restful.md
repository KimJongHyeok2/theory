## REST(Representational State Transfer)
자원을 이름(자원의 표현)으로 구분하여 해당 자원의 상태(정보)를 주고 받는 모든 것을 의미하며 월드 와이드 웹(www)과 같은 분산 하이퍼미디어 시스템을 위한 소프트웨어 개발 아키텍처의 한 형식이다. 기본적으로 HTTP 프로토콜을 그대로 활용하기 때문에 웹의 장점을 최대한 활용할 수 있는 아키텍처 스타일이다.

<h3>장점 및 단점</h3>
<ul>
  <li>
    장점
    <ul>
      <li>HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구축할 필요가 없다.</li>
      <li>HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.</li>
      <li>하이퍼미디어 API의 기본을 충실히 지키면서 범용성을 보장한다.</li>
      <li>REST API 메시지가 의도하는 바를 명확하게 나타내므로 쉽게 파악할 수 있다.</li>
      <li>서로 간의 의존성이 줄어들게 된다.</li>
    </ul>
  </li>
  <li>
    단점
    <ul>
      <li>표준이 존재하지 않는다.</li>
      <li>사용할 수 있는 메소드가 4가지 밖에 없다.(HTTP Method의 형태가 제한적)</li>
      <li>브라우저를 통해 테스트할 일이 많은 서비스라면 쉽게 고칠 수 있는 URL보다 Header값이 왠지 더 어렵게 느껴진다.</li>
      <li>구형 브라우저가 제대로 지원해주지 못하는 부분이 존재한다.(PUT, DELETE, pushState)</li>
    </ul>
  </li>
</ul>

<h3>구성요소</h3>
<ul>
  <li>
    자원(Resource): URI
    <ul>
      <li>모든 자원에 고유한 ID가 존재하고, 이 자원은 Server에 존재한다.</li>
      <li>자원을 구별하는 ID는 '/groups/:group_id'와 같은 HTTP URI다.</li>
      <li>Client는 URI를 이용해서 자원을 지정하고 해당 자원의 상태(정보)에 대한 조작을 Server에 요청한다.</li>
    </ul>
  </li>
  <li>
    행위(Verb): HTTP Method
    <ul>
      <li>HTTP 프로토콜의 Method를 사용한다.</li>
      <li>HTTP 프로토콜은 GET, POST, PUT, DELETE와 같은 메소드를 제공한다.</li>
    </ul>
  </li>
  <li>
    표현(Representation of Resource)
    <ul>
      <li>Client가 자원의 상태(정보)에 대한 조작을 요청하면 Server는 이에 적절한 응답(Representation)을 보낸다.</li>
      <li>REST에서 하나의 자원은 JSON, XML, TEXT, RSS 등 여러 형태의 Representation으로 나타내어 질 수 있다.</li>
      <li>JSON 혹은 XML을 통해 데이터를 주고 받는 것이 일반적이다.</li>
    </ul>
  </li>
</ul>

## 레퍼런스
https://nesoy.github.io/articles/2017-02/REST<br>
https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html
