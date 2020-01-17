React에서 DOM을 한번 Mount 한 뒤, 다음 렌더링 결과와 이전 결과의 비교는 빠르다. 하지만 최적화를 통해 React의 성능을 좀 더 향상시킬 수 있고 앱의 규모에 따라 최적화가 꼭 필요하다.

**클래스형 컴포넌트의 경우는 PureComponent** 를 확장, **함수형 컴포넌트의 경우 React에서 고차 컴포넌트(Higher Order Component, HOC)인 React.memo()** 를 제공한다.

<h3>PureComponent</h3>

LifeCycleAPI인 shouldComponentUpdate에서 **얕은 비교(Shallow Compare)** 를 통해 DOM의 업데이트 여부를 결정한다.(shouldComponentUpdate를 다루는 방식을 제외하곤 Component와 동일하다.)

얕은 비교란?
<ul>
  <li>변수와 문자열에서는 값을 비교</li>
  <li>Object에서는 Reference를 비교</li>
</ul>

```javascript
class MyComponent extends PureComponent {
  ...
}

export deafult MyComponent;
```

비교 방식을 변경하거나 고도화를 하고싶다면(Deep Compare) shouldComponentUpdate를 직접 구현하면 된다.

<h3>React.memo()</h3>

고차 컴포넌트(Higher Order Component, HOC)로 렌더링 결과를 메모이징(Memoizing)하여 불필요한 리렌더링을 건너뛴다.


```javascript
const MyComponent = () => {
  ...
};

export default React.memo(MyComponent);
```

PureComponent와 동일하게 **얕은 비교** 를 통해 DOM 업데이트 여부를 결정하며, Props의 변경이 없는 한 기존에 메모이징된 내용을 그대로 사용한다.
마찬가지로 비교 방식을 변경하거나 고도화를 하고싶다면 두번째 매개변수로 비교함수를 만들어서 넘겨준다.

```javascript
const compare = (prevProps, nextProps) => {
    ...
}

export default React.memo(MyComponent, compare);
```

<h3>React.memo()를 사용하지 말아야할 경우</h3>

성능 관련 변경이 잘못 적용된다면 오히려 성능이 악화될 수 있기 때문에 무조건 사용한다고 좋은 것이 아니라 현명하게 사용해야 한다.

대표적인 예로 콜백 함수를 Props로 넘겨주는 경우가 있다.

```javascript
function sumFactory() {
  return (a, b) => a + b;
}

const sum1 = sumFactory();
const sum2 = sumFactory();

console.log(sum1 === sum2); // => false
console.log(sum1 === sum1); // => true
console.log(sum2 === sum2); // => true

const MyComponent = () => {
  return (
    <ChildComponent 
      onHandle={() => alert('Callback')}
    />
  );
};
```

함수 객체는 "일반" 객체와 동일한 비교 원칙을 따르며 오직 자신에게만 동일하다. 때문에 위의 경우 콜백 함수 때문에 지속적으로 리렌더링이 발생하며 메모이제이션이 중단되게 된다.

이 문제를 해결하려면 onHandle의 Props를 매번 동일한 콜백 인스턴스로 설정해야 한다. 이는 Hooks의 useCallback 함수를 통해 콜백 인스턴스를 보존시키어 해결할 수 있다.

```javascript
const onHandle = useCallback(() => {
  ...
}, []); // 컴포넌트가 처음 렌더링 될 때만 생성

const MyComponent = () => {
  return (
    <ChildComponent 
      onHandle={onHandle}
    />
  );
};

export default React.memo(MyComponent);
```

항상 성능상 이점을 측정하기 위해 React Devtools의 profilling을 사용해서 확인해보는 것이 좋다.

## 레퍼런스
https://ui.toast.com/weekly-pick/ko_20190731/<br>
https://medium.com/@async3619/when-to-use-component-or-purecomponent-b810897a19a2
