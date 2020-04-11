## Next.js
React 어플리케이션의 SSR(Server Side Rendering)을 쉽게 구현 할 수 있게 도와주는 간단한 프레임워크이다.

<h3>핵심 기능</h3>
<ul>
  <li>코드 스플리팅</li>
  <li>간단한 클라이언트 사이드 라우팅</li>
  <li>커스텀 API 서버 (as - 라우트 마스킹)</li>
  <li>Express나 그 어떤 Node.js 서버와 함께 사용 가능</li>
  <li>Hot Module Replacement를 지원하는 Webpack 기반 작업환경</li>
  <li>Babel / Webpack 환경설정 커스터마이징</li>
</ul>

<h3>환경 설정</h3>
<pre>
mkdir hello-next
cd hello-next
yarn init -y
yarn add react react-dom next
mkdir pages
</pre>
<pre>
{
  "name": "hello-next",
  "version": "1.0.0",
  "license": "MIT",
  "scripts": {
    "dev": "next"
  },
  "dependencies": {
    "next": "^2.1.0",
    "react": "^15.4.2",
    "react-dom": "^15.4.2"
  }
}
</pre>

<h3>Deployment</h3>

프로젝트를 완성하고 릴리즈 할때 또 다른 명령어를 사용한다. Next.js 개발사 zeit에서 쉽게 프로젝트를 올릴 수 있는 now를 서비스를 제공해준다.
<pre>
yarn global add now
</pre>

<h3>규칙</h3>

pages 폴더에 라우팅 url과 동일한 이름의 컴포넌트를 생성해야한다. pages 컴포넌트가 next 라우팅과 동일하게 mapping 되기 때문에 이 규칙은 반드시 지켜야한다.

## 레퍼런스
<a href="https://velopert.com/3293">https://velopert.com/3293</a><br>
https://velog.io/@jakeseo_me/Next.js-%EB%B9%A8%EB%A6%AC-%EB%B0%B0%EC%9A%B0%EA%B8%B0-y0jz9oebn0<br>
https://velog.io/@jeff0720/Next.js-%EA%B0%9C%EB%85%90-%EC%9D%B4%ED%95%B4-%EB%B6%80%ED%84%B0-%EC%8B%A4%EC%8A%B5%EA%B9%8C%EC%A7%80-%ED%95%B4%EB%B3%B4%EB%8A%94-SSR-%ED%99%98%EA%B2%BD-%EA%B5%AC%EC%B6%95
