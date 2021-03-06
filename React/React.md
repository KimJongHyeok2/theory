## React
페이스북에서 제공해주는 프론트엔드 라이브러리이다. 컴포넌트 기반으로 되어있어서 컴포넌트에 데이터를 내려주면 개발자가 설계한대로 UI가 만들어져 사용자에게 보여진다.

<h3>React를 사용하는 이유</h3>

사실 React를 사용하지 않아도 얼마든지 웹 페이지를 만들 수 있지만 HTML, CSS 등으로만 만들어진 웹페이지는 동적인 데이터를 UI에 뿌려주기에는 적합하지 않다. React를 이용한다면 사용자와 상호작용할 수 있는 UI를 손쉽게 만들어 줄 수 있다.

<h3>React의 특징</h3>
<ul>
  <li>
    Component<br>
    React는 Component 기반의 라이브러리이다. UI를 하나의 큰 덩어리로 생각한다면 Component는 그 덩어리를 이루는 아주 작은 요소들 이라고 생각하면된다. 그런 요소들을 설계해서 쌓아 올리면 하나의 UI가 만들어진다. 그런 작은 Component들로 쪼개져 있기 때문에 전체 코드를 파악하기가 상대적으로 쉬운듯 하다. 작은 Component들은 다른 화면에서도 사용될 수 있는 재사용성을 가지고 있기 때문에 똑같은 코드를 반복적으로 입력할 필요가 없어서 효율적이며 Component의 종류는 클래스형(stateful)과 함수형(stateless)으로 나누어진다.
  </li>
  <li>
    One Wat Data Flow<br>
    React는 데이터의 흐름이 한 방향으로만 흐른다. 데이터가 내려가기만 하지 밑에서 데이터를 올려줄 수는 없다. 그래서 부모의 데이터를 바꿔주기 위해서는 state를 이용해야한다.
  </li>
  <li>
    Props and State<br>
    <ul>
      <li>
        props<br>
        부모 Component에서 자식 Component로 전달해 주는 데이터를 말한다. 즉, 읽기 전용 데이터라고 생각하면 된다. 자식 Component에서 전달 받은 props는 변경이 불가능하고 props를 전달해준 최상위 부모 Component에서만 props를 변경할 수 있다.
      </li>
      <li>
        state<br>
        동적인 데이터를 다룰 때 사용한다. 사용자와의 상호작용을 통해 데이터를 동적으로 변경을 해야할 때 사용한다. state는 클래스형 Component에서만 사용할 수 있는데 각각의 state는 독립적이라 다른 Component의 직접적인 접근은 불가능하다. 그러나 자신보다 상위에 있는 state는 변경이 가능한데 state를 변경해주는 함수를 props로 받는다면 state의 변경이 가능하다. 주의해야할 점은 props로 넘겨줄 때 this의 binding을 신경써줘야 한다.
      </li>
    </ul>
  </li>
  <li>
    Virtual DOM<br>
    가상의 Document Object Model을 말한다. 일반적으로 HTML 코드를 작성하고 웹 브라우저에서 HTML 파일을 열게되면, HTML 코드들이 DOM을 만들게된다. 그리고 만약 HTML 코드의 특정한 부분이 변경되게 된다면 전체 DOM을 새롭게 만들게 되어 비효율적인 구조이다. 이러한 문제점들은 React에서 해결이 된다. React는 가상의 DOM을 만들어서 진짜 DOM과 비교하여 변경 사항이 있을 경우 전체를 새롭게 만드는게 아니라 변경된 부분만 진짜 DOM에 반영하는 방식으로 작업을 수행한다. 따라서 앱의 효율성과 속도를 높일 수 있게 된다.
  </li>
</ul>

## 출처
https://velog.io/@stampid/React%EB%9E%80

## 레퍼런스
https://velopert.com/3612
