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
레퍼런스 : <a href="https://velopert.com/3293">https://velopert.com/3293</a>
