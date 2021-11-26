### node.js express

간단 예제 Hello World 구문 출력하기

```js
const express = require("express");
const app = express();
const port = 3000;

app.get("/", (req, res) => {
  res.send("Hello World");
});

app.listen(port, () => {
  console.log(`Example app listening at http://localhost:${port}`);
});
```

### 미들웨어

미들웨어 함수는 요청 오브젝트(req), 응답 오브젝트 (res), 그리고 애플리케이션의 요청-응답 주기 중 그 다음의 미들웨어 함수 대한 액세스 권한을 갖는 함수입니다. 그 다음의 미들웨어 함수는 일반적으로 next라는 이름의 변수로 표시됩니다.

미들웨어 함수는 다음과 같은 태스크를 수행할 수 있습니다.

- 모든 코드를 실행.
- 요청 및 응답 오브젝트에 대한 변경을 실행.
- 요청-응답 주기를 종료.
- 스택 내의 그 다음 미들웨어를 호출.
- 현재의 미들웨어 함수가 요청-응답 주기를 종료하지 않는 경우에는 next()를 호출하여 그 다음 미들웨어 함수에 제어를 전달해야 합니다. 그렇지 않으면 해당 요청은 정지된 채로 방치됩니다.
  미들웨어 함수를 로드하려면 미들웨어 함수를 지정하여 app.use()를 호출하십시오. 예를 들면, 다음의 코드는 루트 경로(/)로 라우팅하기 전에 myLogger 미들웨어 함수를 로드합니다.

```js
var express = require("express");
var app = express();

var myLogger = function (req, res, next) {
  console.log("LOGGED");
  next();
};

app.use(myLogger);

app.get("/", function (req, res) {
  res.send("Hello World!");
});

app.listen(3000);
// 요청을 받을떄마다 logged 라는 메시지를 터미널에 인쇄함
```

예제 2

```js
var express = require("express");
var app = express();

var requestTime = function (req, res, next) {
  req.requestTime = Date.now();
  next();
};

app.use(requestTime);

app.get("/", function (req, res) {
  var responseText = "Hello World!";
  responseText += "Requested at: " + req.requestTime + "";
  res.send(responseText);
});

app.listen(3000);
```

오류처리하는 미들웨어!

```js
app.use(function (err, req, res, next) {
  console.error(err.stack);
  res.status(500).send("Something broke!");
});
```

### req.query vs req.params

req.params
서버에서 params요청으로 받을수있는것은 정해진값? 이라 생각할수있을거같은데
예를 들어 /user/:name 경로가 있으면 "name"속성을 req.params.name으로 사용할 수 있다.

req.query
이 속성은 경로의 각 쿼리 문자열 매개 변수에 대한 속성이 포함 된 개체다.
예를 들어 https://query/search?searchWord=구글검색 이면

### express.json

json(strict)를 사용하게되면 어레이와 오브젝트만 받아들이고 다른것은 받아드리지않는다  
그렇기때문에 false를 사용해서 다른 값도 받아들이게 할수있다.
