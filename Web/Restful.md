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

<h3>특징</h3>
<ul>
  <li>
    Server-Client(서버-클라이언트 구조)
    <ul>
      <li>
        자원이 있는 쪽이 Server, 자원을 요청하는 쪽이 Client가 된다.
        <ul>
          <li>REST Server: API를 제공하고 비즈니스 로직 처리 및 저장을 책임진다.</li>
          <li>Client: 사용자 인증이나 context(세션, 로그인 정보) 등을 직접 관리하고 책임진다.</li>
        </ul>
      </li>
      <li>서로 간의 의존성이 줄어든다.</li>
    </ul>
  </li>
  <li>
    Stateless(무상태)
    <ul>
      <li>HTTP 프로토콜은 Stateless Protocol이므로 REST 역시 무상태성을 갖는다.</li>
      <li>
        Client의 context를 Server에 저장하지 않는다.
        <ul>
          <li>즉, 세션/쿠키와 같은 context 정보를 신경쓰지 않아도 되므로 구현이 단순해진다.</li>
        </ul>
      </li>
      <li>
        Server는 각각의 요청을 완전히 별개의 것으로 인식하고 처리한다.
        <ul>
          <li>각 API 서버는 Client의 요청만을 단순 처리한다.</li>
          <li>즉, 이전 요청이 다음 요청의 처리에 연관되어서는 안된다.</li>
          <li>물론 이전 요청이 DB를 수정하여 DB에 의해 바뀌는 것은 허용한다.</li>
          <li>Server의 처리 방식에 일관성을 부여하고 부담이 줄어들며, 서비스의 자유도가 높아진다.</li>
        </ul>
      </li>
      <li>
        Cacheable(캐시 처리 가능)
        <ul>
          <li>
            웹 표준 HTTP 프로토콜을 그대로 사용하므로 웹에서 사용하는 기존의 인프라를 그대로 활용할 수 있다.
            <ul>
              <li>즉, HTTP가 가진 가장 강력한 특징 중 하나인 캐싱 기능을 적용할 수 있다.</li>
              <li>HTTP 프로토콜 표준에서 사용하는 Last-Modified 태그나 E-Tag를 이용하면 캐싱 구현이 가능하다.</li>
            </ul>
          </li>
          <li>대량의 요청을 효율적으로 처리하기 위해 캐시가 요구된다.</li>
          <li>캐시 사용을 통해 응답시간이 빨라지고 REST Server 트랜잭션이 발생하지 않기 때문에 전체 응답시간, 성능, 서버의 자원 이용률을 향상시킬 수 있다.</li>
        </ul>
      </li>
    </ul>
  </li>
  <li>
    Layered System(계층화)
    <ul>
      <li>Client는 REST API Server만 호출한다.</li>
      <li>
        REST Server는 다중 계층으로 구성될 수 있다.
        <ul>
          <li>API Server는 순수 비즈니스 로직을 수행하고 그 앞단에 보안, 로드밸런싱, 암호화, 사용자 인증 등을 추가하여 구조상의 유연성을 줄 수 있다.</li>
          <li>또한 로드밸런싱, 공유 캐시 등을 통해 확장성과 보안성을 향상시킬 수 있다.</li>
        </ul>
      </li>
      <li>PROXY, 게이트웨이 같은 네트워크 기반의 중간 매체를 사용할 수 있다.</li>
    </ul>
  </li>
  <li>
    Code-On-Demand(optional)
    <ul>
      <li>Server로부터 스크립트를 받아서 Client에서 실행한다.</li>
      <li>반드시 충족할 필요는 없다.</li>
    </ul>
  </li>
  <li>
    Uniform Interface(인터페이스 일관성)
    <ul>
      <li>URI로 지정한 Resource에 대한 조작을 통일되고 한정적인 인터페이스로 수행한다.</li>
      <li>
        HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
        <ul>
          <li>특정 언어나 기술에 종속되지 않는다.</li>
        </ul>
      </li>
    </ul>
  </li>
</ul>

<h3>REST API의 개념</h3>
<ul>
  <li>
    API(Application Programming Interface)란
    <ul>
      <li>데이터와 기능의 집합을 제공하여 컴퓨터 프로그램간 상호작용을 촉진하며, 서로 정보를 교환 가능하도록 하는 것</li>
    </ul>
  </li>
  <li>
    REST API의 정의
    <ul>
      <li>REST 기반으로 서비스 API를 구현한 것</li>
      <li>최근 OpenAPI(누구나 사용할 수 있도록 공개된 API: 구글맵, 공공 데이터 등), 마이크로 서비스(하나의 큰 애플리케이션을 여러 개의 작은 애플리케이션으로 쪼개어 변경과 조합이 가능하도록 만든 아키텍처) 등을 제공하는 업체 대부분은 REST API를 제공한다.</li>
    </ul>
  </li>
</ul>

<h3>REST API의 특징</h3>
<ul>
  <li>사내 시스템들도 REST 기반으로 시스템을 분산해 확장성과 재사용성을 높여 유지보수 및 운용을 편리하게 할 수 있다.</li>
  <li>REST는 HTTP 표준을 기반으로 구현하므로, HTTP를 지원하는 프로그램 언어로 클라이언트, 서버를 구현할 수 있다.</li>
  <li>즉, REST API를 제작하면 델파이 클라이언트 뿐 아니라, 자바, C#, 웹 등을 이용해 클라이언트를 제작할 수 있다.</li>
</ul>

<h3>REST API 설계 기본 규칙</h3>
참고 리소스 원형
<ul>
  <li>도큐먼트: 객체 인스턴스나 데이터베이스 레코드와 유사한 개념</li>
  <li>컬렉션: 서버에서 관리하는 디렉터리라는 리소스</li>
  <li>스토어: 클라이언트에서 관리하는 리소스 저장소</li>
</ul>
<ul>
  <li>
    URI는 정보의 자원을 표현해야한다.
    <ul>
      <li>resource는 동사보다는 명사를, 대문자보다는 소문자를 사용한다.</li>
      <li>resource의 도큐먼트 이름으로는 단수 명사를 사용해야 한다.</li>
      <li>resource의 컬렉션 이름으로는 복수 명사를 사용해야 한다.</li>
      <li>resource의 스토어 이름으로는 복수 명사를 사용해야 한다.</li>
    </ul>
  </li>
  <li>
    자원에 대한 행위는 HTTP Method(GET, PUT, POST, DELETE 등)로 표현한다.
    <ul>
      <li>URI에 HTTP Method가 들어가면 안된다.</li>
      <li>URI에 행위에 대한 동사 표현이 들어가면 안된다.</li>
      <li>경로 부분 중 변하는 부분은 유일한 값으로 대체한다.</li>
    </ul>
  </li>
</ul>

<h3>REST API 설계 규칙</h3>
<ul>
  <li>
    슬래시 구분자(/)는 계층 관계를 나타내는데 사용한다.
    <ul>
      <li>EX) http://restapi.example.com/houses/apartments</li>
    </ul>
  </li>
  <li>
    URI 마지막 문자로 슬래시(/)를 포함하지 않는다.
    <ul>
      <li>URI에 포함되는 모든 글자는 리소스의 유일한 식별자로 사용되어야 하며 URI가 다르다는 것은 리소스가 다르다는 것이고, 역으로 리소스가 다르면 URI도 달라져야 한다.</li>
      <li>REST API는 분명한 URI를 만들어 통신을 해야 하기 때문에 혼동을 주지 않도록 URI 경로의 마지막에는 슬래시(/)를 사용하지 않는다.</li>
      <li>EX) http://restapi.example.com/houses/apartments</li>
    <ul>
  </li>
</ul>

## 레퍼런스
https://nesoy.github.io/articles/2017-02/REST<br>
https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html
