## Redux
JavaScript 어플리케이션에서 data-state와 UI-state를 관리해주는 도구이다. 이는 상태적 데이터 관리가 시간의 흐름에 따라 복잡해질 수 도 있는 싱글 페이지 어플리케이션(Single Page Application)에서 매우 유용하게 사용된다. 그리고 Redux는 React 외에도, JQuery 혹은 Angular를 사용하는 어플리케이션에도 사용 될 수 있다.

<ul>
  <li>store: React.js 프로젝트에서 사용하는 모든 동적 데이터들을 담아두는 곳</li>
  <li>action: 어떤 변화가 일어나야 할 지 나타내는 객체</li>
  <li>reducer: action 객체를 받았을 때, 데이터를 어떻게 바꿀지 처리할지 정의하는 객체</li>
  <li>store.getState():  현재 스토어에있는 데이터를 반환</li>
  <li>store.dispatch(ACTION): 상태값을 수정 할 때 사용되는 메소드</li>
</ul>

## Flux 패턴

React는 MVC(Model-View-Controller 패턴에서 V에 해당하는 View에 집중하였고 MVC는 아래와 같은 패턴이다.

<img src="https://user-images.githubusercontent.com/47962660/68994835-ac93ba00-08ca-11ea-8425-527586585ba1.png"/>

여기서 View가 많아진다면 아래와 같이 복잡해질 것 이다.

<img src="https://user-images.githubusercontent.com/47962660/68994867-ee246500-08ca-11ea-9904-4adb3719770c.png"/>

Model & View가 추가될 때 마다 복잡도가 증가하고, 프로젝트 규모가 기하 급수적으로 늘어나며 Model & View의 관계도를 파악하기 어려워진다.
그래서 이러한 MVC 패턴의 단점을 보완해줄 수 있는 패턴이 Flux 패턴이다.

<img src="https://user-images.githubusercontent.com/47962660/68994891-317ed380-08cb-11ea-909c-c47283744698.png"/>

Flux 패턴에서 Store는 어플리케이션의 모든 데이터 변화를 담고있다. Action이 발생했을 때, Dispatcher는 Store를 어떻게 갱신할지 결정한다. 이 후 Store가 변경되면 Store 내부의 데이터도 바뀌므로 View도 갱신된다. 정리하자면, Dispatcher가 Action으로 인한 데이터 변경로직을 결정하면 Store에 변경된 데이터가 쌓여 View도 갱신해주는 것이다.

결국 Redux는 Flux 패턴을 좀 더 쉽고 정돈된 형태로 쓸 수 있게 도와주는 라이브러리(State Management Library)이며, JavaScript Application에서 Data-State와 UI-state를 관리해주는 도구이다.

## 레퍼런스
https://engineering.huiseoul.com/react-redux-intro-bbff95b14cdf<br>
https://delivan.dev/react/stop-asking-if-react-hooks-replace-redux-kr/
