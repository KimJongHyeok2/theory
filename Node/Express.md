## Express.js
Node.js 상에서 동작하는 웹 개발 프레임워크이다. Express.js 이외에도 Hapi.js, Koa.js 등 다양한 웹 프레임워크가 있지만 현재까지 가장 많이 사용하는 것이 바로 익스프레스 엔진이다.

<h3>Express 라우팅</h3>

라우팅은 애플리케이션 엔드 포인트(URI)정의 및 URI가 클라이언트 요청에 응답하는 방식을 말한다.

```javascript
const express = require('express'); //requre 는 module.exports를 리턴한다 (함수로 모듈을 가지고 온다.)
const app = express();
const PORT = 4000; // PORT 번호

const handlehome = (req,res) => {
  console.log(req);
  res.send("Hello From Home");
}

const handleProfile = (req,res) => {
  res.send("You are profile");
}

app.get('/',handlehome); //root로 접속한 경로에 response로 helloworld를 받아서 출력해준다.
app.get('/profile',handleProfile); //경로 http://localhost:4000/profile

const handleListening = () =>{
  console.log(`Listening on : http://localhost:${PORT}`);
}

app.listen(PORT,handleListening); // port번호 설정
```

## 레퍼런스
http://webframeworks.kr/getstarted/expressjs/
