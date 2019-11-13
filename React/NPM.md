## NPM(Node Package Manager)
Node의 모듈을 관리해주는 패키지 매니저이다. (MAVEN과 비슷한 개념)

<h3>명령어 정리</h3>
<table>
  <thead>
    <tr>
      <td>명령어</td><td>설명</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>npm install</td><td>패키지 설치</td>
    </tr>
    <tr>
      <td>npm init</td><td>package.json 생성</td>
    </tr>
    <tr>
      <td>npm install@버전</td><td>특정 버전의 패키지 설치</td>
    </tr>
    <tr>
      <td>npm install 주소</td><td>특정한 저장소에 있는 패키지 설치(주로 GitHub)</td>
    </tr>
    <tr>
      <td>npm install OO --save-dev || -D</td><td>devDependecies에 추가</td>
    </tr>
    <tr>
      <td>npm install OO -g</td><td>글로벌 패키지에 추가(다른 프로젝트에서도 사용가능)</td>
    </tr>
    <tr>
      <td>npm update</td><td>설치한 패키지 업데이트</td>
    </tr>
    <tr>
      <td>npm dedupe</td><td>중복된 패키지 정리</td>
    </tr>
    <tr>
      <td>npm docs</td><td>패키지에 대한 설명(npm 홈페이지에서 확인하는 것을 권장)</td>
    </tr>
    <tr>
      <td>npm publish</td><td>패키지를 직접 출시하거나 버전 업그레이드</td>
    </tr>
    <tr>
      <td>npm deprecate</td><td>이미 출시한 패키지를 사용하지 않도록 권고</td>
    </tr>
    <tr>
      <td>npm unpublish</td><td>publish한 패키지를 다시 unpublish</td>
    </tr>
    <tr>
      <td>npm star</td><td>특정인이 star한 패키지 목록</td>
    </tr>
    <tr>
      <td>npm version [버전]</td><td>버전 업데이트</td>
    </tr>
    <tr>
      <td>npm start</td><td>package.json의 scripts에 있는 start 명령어를 실행(따로 설정하지 않으면 node server.js 실행</td>
    </tr>
    <tr>
      <td>npm stop</td><td>종료</td>
    </tr>
    <tr>
      <td>npm restart</td><td>재시작</td>
    </tr>
    <tr>
      <td>npm test</td><td>test 명령어</td>
    </tr>
    <tr>
      <td>npm run</td><td>이 외의 scripts를 실행한다.(Ex. build = npm run build)</td>
    </tr>
    <tr>
      <td>npm cache</td><td>npm 내의 cache 확인</td>
    </tr>
    <tr>
      <td>npm cache clean</td><td>cache를 지움</td>
    </tr>
    <tr>
      <td>npm rebuild</td><td>npm 재설치, 주로 에러 발생 시 npm cache clean 후 실행</td>
    </tr>
  </tbody>
</table>
