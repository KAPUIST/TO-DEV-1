### CORS

최근에 웹 어플리케이션이 고도화 되면서 옛날 방식이아닌 여러서버에서 리소스를 받아오는 것때문에 SAME origin 이아닌
cross origin resource sharing (cors)

보안상의 이유로 브라우저들은 크로스 도메인 요청은 기본작으로 제한되어있다 하지만 개발자들의 무수한요청이있어서 서버가 Allow한 범위내에서 cross origin 요청을 허용하게됨

허용가능한 요청
'access-control-allow-origin':'\*'
'access-control-allow-methods' : 'GET , POST , PUT , DELETE, OPTIONS'
'access-control-allow-headers': 'content-type, accept'
'access-control-max-age':'10'

- 모든 도메인은(\*)을 허용한다
- 메소드는 GET POSY PUT DELETE OPTIONS만 허용한다
- 헤더에는 content-type 과 accept 만 사용가능하다
- preflight request는 10초까지 하용된다

### HTTP 트랜잭션 해부

트랜잭션이란 데이터베이스의 상태를 변화시키기위해서 수행하는 작업의 단위를 뜻합니다
데이터베이스의 상태를 변화시킨다는것은 무얼의미 하는걸까
간단하게 말해서
SELECT
INSERT
DELETE
UPDATE
를 이용하여 데이터 베이스를 접근하는것을 의미한다
서버생성

```js
const http = require("http");
const server = http.createServer((request, response) => {});
```

모든 node 웹 서버 애플리케이션은음
웹 서버 객체를 만들어야 합니다. 이 때 createServer를 이용합니다
이 서버로 오는 HTTP 요청마다 createServer에 전달된 함수가 한번씩 호출됩니다.

#### 요청바디

POST 나 PUT 요청을 받을때 애플리케이션에 요청바디는 중요할것입니다. 요청 헤더에 접근하는 것보다 바디 데이터를 받는 것은 좀더 어렵습니다.
각 'data' 이벤트에서 발생시킨 청크는 Buffer입니다. 이 청크가 문자열 데이터라는 것을 알고 있다면 이 데이터를 배열에 수집한 다음 'end' 이벤트에서 이어 붙인 다음 문자열로 만드는 것이 가장 좋습니다.

```js
let body = [];
request
  .on("data", (chunk) => {
    body.push(chunk);
  })
  .on("end", () => {
    body = Buffer.concat(body).toString();
  });
```

대략 지금까지 살표본내용

```js
const http = reqiure("http");

http.createServer((request, response) => {
  let body = [];
  request
    .on("error", (err) => {
      console.error(err);
    })
    .on("data", (chunk) => {
      body.push(chunk);
    })
    .on("end", () => {
      body = Buffer.concat(body).toString();
    });
});
```

이것을 실행하면 요청을 받을수는 있지만 응답할수는 없다

#### HTTP 상태코드

따로설정하지않으면 응답의 HTTP상태 코드는 항상 200 입니다
물론 모든 HTTP 응답이 이를 보장하는 것은 아니고 어떤 경우에는 다른 상태 코드를 보내기를 원할 것입니다. 상태 코드를 변경하려면 statusCode 프로퍼티를 설정해야 합니다.

```js
response.statusCode = 404; // 클라이언트에게 리소스를 찾을 수 없다고 알려줍니다.
```

#### 응답헤더설정

```js
response.setHeader("Content-Type", "application/json");
response.setHeader("X-Powered-By", "bacon");
```

응답에 헤더를 설정할때 헤더이름의 대소문자는 중요하지않습니다. 헤더를 여러번 설정한다면 마지막에 설정한 값을 보낸다!

좀더 명시적으로 응답 스트림에 헤더를 작성할수있다 바로 writeHead 메소드를 사용하는 것입니다 이메서드는 스트림 상태코드와 헤더를 작성합니다

```js
response.writeHead(200, {
  "Content-Type": "application/json",
  "X-Powered-By": "bacon",
});
```

일단 암묵적이든 명시적이든 헤더를 설정하고 나면 응답데이터를 전송할 준비가 된것입니다

#### Buffer란 무엇인가

Buffer클래스는 바이너리 데이터들의 스트림을 직접 다루기위해 Node.js API에 추가 되었습니다.

##### 바이너리 데이터? 이게 뭘까?

우리는 컴퓨터가 이진수로 데이터를 저장하고 표현한다는걸 이미 알고있습니다. 이진수는 단순히 1과 0의 집합입니다. 예를들어, 다음은 서로 다른 이진수 5개이며, 이 이진수들은 서로다른 1과 0의 집합입니다.

10, 01, 001, 1110, 00101011

각각 이진수에서 1 혹은 0으로 되어있는 자리를 비트(bit)라고 합니다. 이는 Binary digIT의 약자입니다.

##### Stream

Node.js 에서의 스트림은 간단하게 한 지점에서 다른 지점으로 이동하는 일련의 데이터를 의미합니다. 전체적인 의미로는, 만약 우리가 어떤 방대한 양의 데이터를 처리해야 할때, 모든 데이터가 전부다 사용가능 할때까지 기다리지 않아도 된다는 것입니다.

기본적으로 큰 데이터는 청크단위로 세분화되어 전송됩니다. 이말은, 처음 설명했던 Buffer의 정의에 따르면, 파일시스템에서 바이너리 데이터들이 이동한다는걸 의미합니다. 예를들어, file1.txt의 텍스트를 file2.txt로 옮기는 걸 의미합니다.

하지만, Streaming 하는동안에 buffer라는 것이 어떻게 바이너리 데이터를 다룰 수 있게 도와준다는 것일까요? 정확히 buffer는 무엇일까요?
