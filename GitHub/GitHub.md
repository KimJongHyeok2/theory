## Git
프로그램 등의 소스 코드 관리를 위한 분산 버전 관리 시스템이다. Git의 작업 폴더는 모두 기록하고 있어서 추적이 가능하고, 완전한 형태의 저장소이다.

## GitHub
Git을 호스팅해주는 웹 서비스이며, Git 저장소 서버를 대신 유지 및 관리해주는 서비스이다.

<h5>기본적인 명령어 정리</h5>
<table>
  <thead>
    <tr>
      <td>명령어</td><td>설명</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>git config --global <이메일 주소></td><td>초기설정</td>
    </tr>
    <tr>
      <td>git config --global <이름></td><td>초기설정</td>
    </tr>
    <tr>
      <td>git init</td><td>해당 폴더에 Git을 사용할 것을 알림, master branch가 생성되고 git bash 현재 폴더명에 branch 이름이 추가된다.</td>
    </tr>
    <tr>
      <td>git add .</td><td>현재 폴더의 파일들과 하위 폴더의 파일 모두를 저장할 대상으로 지정한다. 점(.) 대신 각각의 파일 이름을 하나하나 지정할 수 있다.</td>
    </tr>
    <tr>
      <td>git commit -m <내용></td><td>저장과 동시에 메시지를 남긴다.</td>
    </tr>
    <tr>
      <td>git commit -m <내용> --amend</td><td>마지막 커밋을 고친다.</td>
    </tr>
    <tr>
      <td>git commit -C HEAD --amend</td><td>이전 커밋을 수정하고 커밋 메시지를 재사용한다.</td>
    </tr>
    <tr>
      <td>git checked HEAD <파일> [<파일>]</td><td>작업 트리의 변경사항을 돌려놓는다.</td>
    </tr>
    <tr>
      <td>git reset HEAD <파일>[<파일>]</td><td>커밋되지 않고 스테이징된 변경사항을 재설정한다.</td>
    </tr>
    <tr>
      <td>git push</td><td>remote repository로 업로드</td>
    </tr>
    <tr>
      <td>git clone</td><td>git을 포함한 remote repository의 파일들을 local repository에 복사, GitHub에서 zip 파일로 받을 시 .git 폴더가 없음</td>
    </tr>
    <tr>
      <td>git remote add <원격 저장소> <url></td><td>새로운 원격 저장소를 추가한다.</td>
    </tr>
    <tr>
      <td>git branch</td>
      <td>
        <ul>
          <li>독립된 working directory를 의미한다.</li>
          <li>branch를 통해 프로젝트 참여자마다 branch를 가지어 독립된 작업 공간을 갖는다.</li>
          <li>테스트 및 백업 등의 용도로 사용할 수도 있다.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>head</td><td>포인터를 의미하며 지금 작업하고 있는 branch를 가르킨다.</td>
    </tr>
    <tr>
      <td>merge</td>
      <td>
        <ul>
          <li>2개의 branch에서 작업한 각기 다른 내용을 하나로 합치는 것을 의미하며, 현재 branch를 기준으로 병합된다.</li>
          <li>만약 두 branch가 같은 파일의 같은 곳을 수정했다면, 충돌(merge conflict)이 발생해서 이를 해결해야 한다.</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
