## Redux
JavaScript 어플리케이션에서 data-state와 UI-state를 관리해주는 도구이다. 이는 상태적 데이터 관리가 시간의 흐름에 따라 복잡해질 수 도 있는 싱글 페이지 어플리케이션(Single Page Application)에서 매우 유용하게 사용된다. 그리고 Redux는 React 외에도, JQuery 혹은 Angular를 사용하는 어플리케이션에도 사용 될 수 있다.

<ul>
  <li>store: React.js 프로젝트에서 사용하는 모든 동적 데이터들을 담아두는 곳</li>
  <li>action: 어떤 변화가 일어나야 할 지 나타내는 객체</li>
  <li>reducer: action 객체를 받았을 때, 데이터를 어떻게 바꿀지 처리할지 정의하는 객체</li>
  <li>store.getState():  현재 스토어에있는 데이터를 반환</li>
  <li>store.dispatch(ACTION): 상태값을 수정 할 때 사용되는 메소드</li>
<ul>
