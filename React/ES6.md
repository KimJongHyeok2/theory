## ES6 Study
넷스케이프(Netscape)에서 19995년 개발한 자바스크립트(javascript)는 웹 브라우저에서 동적인 기능을 제공하기 위한 언어다. 현재는 대부분의 브라우저에서 이 언어를 제공하고 있다. 그런데 표준 규격없이 여러 브라우저에서 독자적인 특성이 추가되면서 호환성 문제가 발생하기 시작했다. 이에 ECMA 국제 기구에서 "ECMAScript Standard" 라는 표준을 만들게 되었다. 정확히 이야기 하자면 현재의 자바스크립트는 ECMAScript와 BOM(Browser Object Model)와 DOM(Document Object Mdoel)을 포괄하는 개념이다.

<h3>개발자가 필히 알아야할 ES6 10가지 기능</h3>
<ul>
  <li>기본 매개 변수 (Default Parameters)</li>
  <li>템플릿 리터럴 (Template Literals)</li>
  <li>멀티 라인 문자열 (Multi-line Srtings)</li>
  <li>비구조화 할당 (Destructuring Assignment)</li>
  <li>향상된 객체 리터럴 (Enhanced Object Literals)</li>
  <li>화살표 함수 (Arrow Functions)</li>
  <li>Promises</li>
  <li>블록 범위 생성자 Let 및 Const (Block-Scoped Constructs Let and Const)</li>
  <li>클래스 (Classes)</li>
  <li>모듈 (Modules)</li>
</ul>

<h3>let, const</h3>

기존에 자바스크립트에서는 var를 이용하여 변수를 선언하였다. 다른 프로그래밍 언어는 보통 블럭단위(block-level) 유효 범위를 가지고 있지만 이 var는 함수에 대해서만 Scope를 가지고 있다. 그래서 ES6에서는 새로운 키워드인 let을 추가하였다.

<ul>
  <li>
    let의 특징
    <ul>
      <li>블록단위 scope를 가진다.</li>
      <li>글로벌 let 변수는 글로벌 객체의 속성이 아니다.</li>
      <li>for문 등의 루프에서 for(let v...) v를 루프마다 새로 바인딩한다.</li>
      <li>선언 전부터 참조하면 에러가 발생한다.</li>
      <li>같은 let 변수 선언 시 문법 에러가 발생한다.(ES6의 모듈을 사용하여 해결)</li>
    </ul>
  </li>
  <li>
    const의 특징
    <ul>
      <li>let과 동일하나 최초 값 할당 이후 값의 변경이 불가능하다.(변하지 않는 값을 사용 시 이용한다.)</li>
    </ul>
  </li>
</ul>

<h3>Arrow Functions</h3>

함수는 간결해지고 코드는 짧아졌다.
```javascript
const squares = [1, 2, 3].map(x => x * x) // 1, 4, 9
```
자신만의 this를 생성하지 않는다.
```javascript
function NumberEx() {
  var that = this
  that.num = 0;
  setInterval(function add() {
    // setInterval 안에서의 this 는 NumberEx의 this가 아니므로 다른 변수에 this를 지정하여 사용한다.
    that.num++;
    console.log(that.num);
  }, 1000);
}
```
화살표 함수는 자신의 this가 바인드 되지 않기 때문에 함수의 스코프에서의 this가 적용된다.
```javascript
function NumberEx() {
  this.num = 0

  setInterval(() => {
    this.num++ // this is from NumberEx
  }, 1000)
}
```

<h3>Modules</h3>

Export, Import 를 이용해 function이나 variables 들을 다른 곳에서 사용할 수 있다.

```javascript
//  utility.js
export const squares = (arr) => { return arr.map(x => x * x) }

// math.js
import { squares } from "utility"
console.log(squares([1,2,3])) // [1,4,9]
```

<h3>Promise</h3>

비동기 프로세싱을 위해 사용된다. (Asynchronously) 가독성이 좋으며 중첩된 콜백의 단점을 완화한다.
(Callback Hell이라는 Callback 함수가 다시 Callback을 호출하고 또다시 Callback을 호출하는 코드를 읽기도 관리하기도 힘들어지는 것은 완화할 수 있다.)<br><br>

Promise의 세가지 상태
<ul>
  <li>대기중(pending)</li>
  <li>이행됨(fulfilled)</li>
  <li>거부됨(rejected)</li>
</ul>

```javascript
var promiseTest = (num) => {
    return new Promise((resolve, reject) => {
        if (num > 3) {
            resolve(num)
        } else {
            reject("err")
        }
    }
}

promiseTest(5)
    .then(val => console.log(val)) // 5
    .catch(err => console.log(err))
```

<h3>Destructuring Assignment</h3>

<a href="https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment">비구조화 할당</a>
```javascript
// ES5
var name = req.body.name;
var age = req.body.age;
var email = req.body.email;
```
```javascript
// ES6
const {name, age, email} = req.body;
```

<h3>Object Initialize - Property Shorthand</h3>

<a href="https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Object_initializer">객체 초기자</a>
```javascript
// ES5
var name = 'hak'
var age = 27
var email = 'code.ryan.lee@gmail.com'

var datas = {
  name: name,
  age: age,
  email: email
}
```
```javascript
// ES6
let name = 'hak'
let age = 27
let email = 'code.ryan.lee@gmail.com'

let datas = {name, age, email}
let datas2 = {username: name, age, email}
```
## 레퍼런스
https://sanghaklee.tistory.com/54
