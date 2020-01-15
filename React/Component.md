## Component
컴포넌트는 UI의 일부분을 묘사하는 자생적이고 독립적인 아주 작은 엔티티이며 클래스와 함수형 두 가지 유형이 있다.

LifeCycleAPI와 State의 사용이 필요없을 경우, props를 통해 view만을 렌더링하는 경우엔 함수형 컴포넌트를 사용하는 것이 성능이 좀 더 좋다고한다. (React 16에서는 함수형 컴포넌트의 성능이 좀 더 빠르다고 <a href="https://twitter.com/trueadm/status/916706152976707584">페이스북 개발자</a>가 언급하였다고 한다.)

따라서 React App을 Container x Presentational 방식으로 구성할 경우 Container는 클래스형, Presentational 컴포넌트는 함수형 사용한다.

+ React 16.8 버전부터는 함수형 컴포넌트에서 State와 LifeCycleAPI를 사용할 수 있는 Hooks라는 개념이 등장했고 점진적으로 클래스 컴포넌트에만 존재하는 기능등을 추가할 예정이라고 한다. 기존의 클래스 컴포넌트를 전환할 필요는 없지만 상황에 따라 Hooks를 사용하는 것이 유지보수성과 가독성 측면에서 좋다고한다.

## 레퍼런스
https://ko.reactjs.org/docs/hooks-intro.html
