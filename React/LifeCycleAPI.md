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

<h3>constructor</h3>
<pre>
constructor(props){
    super(props);
}
</pre>

생성자 메소드로서 컴포넌트가 처음 만들어 질 때 실행되며
이 메소드에서 기본 state를 설정할 수 있다.

<h3>componentWillMount</h3>
<pre>
componentWillMount(){
}
</pre>

컴포넌트가 DOM 위에 생성되기 전에 실행된다.

<h3>render</h3>

컴포넌트 렌더링을 담당한다.

<h3>componentDidMount</h3>
<pre>
componentDidMount(){
}
</pre>

컴포넌트가 생성된 후 첫 렌더링을 마치고 실행되는 메소드이다

<h3>componentWillReceiveProps</h3>
<pre>
componentWillReceiveProps(){
}
</pre>

컴포넌트가 새로운 props를 받았을 때 실행된다.
이 안에서 this.setState() 를 해도 추가적으로 렌더링하지 않는다.

<h3>shouldComponentUpdate</h3>
<pre>
shouldComponentUpdate(){
}
</pre>

prop 혹은 state 가 변경 되었을 때, 리렌더링을 할지 말지 정하는 메소드이다.

<h3>componentDidUpdate</h3>
<pre>
componentDidUpdate(prevProps, prevState){
}
</pre>

컴포넌트가 리렌더링을 마친 후 실행된다.

<h3>componentWillUnmount</h3>
<pre>
componentWillUnmount(){
}
</pre>

컴포넌트가 DOM 에서 사라진 후 실행되는 메소드이다.

<img src="https://user-images.githubusercontent.com/47962660/69010563-4d09dd00-09a4-11ea-9c5c-08eff2b3f5b9.png"/>

## 레퍼런스
https://velopert.com/1130<br>
https://velog.io/@kyusung/%EB%A6%AC%EC%95%A1%ED%8A%B8-%EA%B5%90%EA%B3%BC%EC%84%9C-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8%EC%99%80-%EB%9D%BC%EC%9D%B4%ED%94%84%EC%82%AC%EC%9D%B4%ED%81%B4-%EC%9D%B4%EB%B2%A4%ED%8A%B8
