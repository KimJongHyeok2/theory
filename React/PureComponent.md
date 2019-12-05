## PureComponent
Component와 매우 유사하지만 한 가지 다른 점이 있다면, React의 LifeCycleAPI 중 하나인 ``shouldComponentUpdate``가 이미 구현되어 있는데 ``props``와 ``state``를 얕은 비교를 통해 비교한 뒤 변경된 것이 있을 때만 리렌더링한다. 즉, ``PureComponent``를 사용하면 React Application의 성능을 향상시키는 데 가장 중요한 것 중 하나인 ``shouldComponentUpdate``를 신경쓰지 않아도 된다. 하지만 ``props``나 ``state``가 복잡한 데이터 구조를 포함하고 있다면, ``props``와 ``state``를 비교하는 과정에서 의도하지 않은 결과가 발생할 수 있다.

## 레퍼런스
https://wonism.github.io/react-pure-component/<br>
https://velog.io/@lesh/PureComponent%EC%99%80-componentShouldUpdate-9cjz3nh0v1<br>
https://medium.com/vingle-tech-blog/react-%EB%A0%8C%EB%8D%94%EB%A7%81-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-f255d6569849
