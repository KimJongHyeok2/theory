## Maven
Apache의 이름 아래 2004년 출시하였고 Ant를 사용하던 개발자들의 불편함을 해소하는 동시에 부가기능을 추가하였다.

<ul>
  <li>빌드를 쉽게 (Making the build process easy)</li>
  <li>pom.xml을 이용한 정형화된 빌드 시스템 (Providing a uniform build system)</li>
  <li>
    뛰어난 프로젝트 정보 제공 (Providing quality project information_
    <ul>
      <li>Change log document created directly from source control</li>
      <li>Cross referenced sources</li>
      <li>Mailing lists</li>
      <li>Dependency list</li>
      <li>Unit test reports including coverage</li>
    </ul>
  </li>
  <li>
    개발 가이드 라인 제공 (Providing guidelines for best practices development)
    <ul>
      <li>Keeping your test source code in a separate, but parallel source tree</li>
      <li>Using test case naming conventions to locate and execute tests</li>
      <li>Have test cases setup their environment and don’t rely on customizing the build for test preparation</li>
    </ul>
  </li>
  <li>새로운 기능을 쉽게 설치할 수 있고 업데이트할 수 있음 (Allowing transparent migration to new features)</li>
</ul>

## Gradle
Ant와 Maven의 장점을 모아 2012년에 출시하였고 Android OS의 빌드 도구로 채택되었다.

<ul>
  <li>Ant처럼 유연한 범용 빌드 도구 (A very flexible general purpose build tool like Ant)</li>
  <li>Maven을 사용할 수 있는 변환 가능 컨벤션 프레임 워크 (Switchable, build-by-convention frameworks a la Maven. But we never lock you in!)</li>
  <li>멀티 프로젝트에 사용하기 좋음 (Very powerful support for multi-project builds)</li>
  <li>Apache Ivy에 기반한 강력한 의존성 관리 (Very powerful dependency management (based on Apache Ivy))</li>
  <li>Maven과 Ivy 레파지토리 완전 지원 (Full support for your existing Maven or Ivy repository infrastructure)</li>
  <li>원격 저장소나, pom, ivy 파일 없이 연결되는 의존성 관리 지원 (Support for transitive dependency management without the need for remote repositories or pom.xml and ivy.xml files)</li>
  <li>그루비 문법 사용 (Groovy build scripts)</li>
  <li>빌드를 설명하는 풍부한 도메인 모델 (A rich domain model for describing your build)</li>
</ul>

## Maven VS Gradle
Maven에는 Gradle과의 비교 문서가 존재하지 않지만, Gradle에는 비교문서가 존재한다. Gradle이 시기적으로 늦게 나온만큼 사용성, 성능 등 비교적 뛰어난 스펙을 가지고있다.

<h3>Gradle이 Maven보다 좋은점</h3>
<ul>
  <li>
    Build라는 동적인 요소를 XML로 정의하기에는 어려운 부분이 많다.
    <ul>
      <li>설정 내용이 길어지고 가독성 떨어짐</li>
      <li>의존관계가 복잡한 프로젝트 설정하기에 부적절</li>
      <li>상속구조를 이용한 멀티 모듈 구현</li>
      <li>특정 설정을 소수의 모듈에서 공유하기 위해서는 부모 프로젝트를 생성하여 상속하게 해야 함 (상속의 단점 생김)</li>
    </ul>
  </li>
  <li>
    Gradle은 Groovy를 사용하기 때문에, 동적인 빌드는 Groovy 스크립트로 플러그인을 호출하거나 직접 코드를 짜면 된다.
    <ul>
      <li>Configuration Injection 방식을 사용해서 공통 모듈을 상속해서 사용하는 단점을 커버했다.</li>
      <li>설정 주입 시 프로젝트의 조건을 체크할 수 있어서 프로젝트별로 주입되는 설정을 다르게 할 수 있다.</li>
    </ul>
  </li>
  <li>스크립트 길이와 가독성 면에서 Gradle(groovy)이 앞선다.</li>
  <li>빌드와 테스트 실행 결과 Gradle이 더 빠르다. (Gradle이 캐시를 사용하기 때문에 테스트 반복 시 차이가 더 커짐)</li>
  <li>의존성이 늘어날 수록 성능과 스크립트 품질의 차이가 심해질 것이다.</li>
</ul>

## Maven VS Gradle Performance Comparison

<ul>
  <li>600명의 엔지니어가 1년동안 1분걸리는 빌드를 매주 42번 빌드를 진행할 때 들어가는 비용</li>
  <li>600 engineers * $1.42/minutes * 42 builds/week * 44 work weeks/year = $1,600,000/year</li>
  <li>Gradle은 메이븐 보다 최대 100배 빠르다.</li>
</ul>

<img src="https://user-images.githubusercontent.com/47962660/70847259-cd3d3880-1ea5-11ea-8bc0-c222b47fa771.png"/>
<img src="https://user-images.githubusercontent.com/47962660/70847318-aaf7ea80-1ea6-11ea-9b6c-e0465dc94835.png"/>
<img src="https://user-images.githubusercontent.com/47962660/70847323-b9460680-1ea6-11ea-92b9-cd5026b7c354.png"/>
<img src="https://user-images.githubusercontent.com/47962660/70847327-c236d800-1ea6-11ea-8a67-98383e0cac24.png"/>

## 출처
https://bkim.tistory.com/13
## 레퍼런스
https://okky.tistory.com/179
