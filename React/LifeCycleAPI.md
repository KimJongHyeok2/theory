<h3>컴포넌트 생성 시 실행 순서</h3>
constructor -> componentWillMount -> render -> componentDidMount<br><br>

<ul>
  <li>
    컴포넌트 제거 시
    <ul>
      <li>componentWillUnmount 메소드만 실행</li>
    </ul>
  </li>
  <li>
    컴포넌트 props 변경 시
    <ul>
      <li>componentWillReceiveProps -> shouldComponentUpdate -> componentWillUpdate -> render -> componentDidUpdate</li>
    </ul>
  </li>
</ul>
