마지막 프로젝트에 앞서서 우리가 기획한 기능 중에 채팅방이 존재하기때문에 실시간 채팅을 위해서 socket.io라는 라이브러리를 공부해 보려한다!!

넌누구냐....

### socket.io

- socket.io는 웹소켓을 이용하여 실시간 데이터 전송을 할수있다
- 클라이언트에서 Event Listener로 새로운 정보를 받아 정보를 업데이트할 수 있다.

공식 문서에 나와있는 내용을보고 만들어보았다.

```js
import express from "express";
import cookieParser from "cookie-parser";
const http = require("http");
const app = express();
const server = http.createServer(app);
const SocketIO = require("socket.io");
const io = SocketIO(server);

app.use(express.urlencoded({ extended: false }));
app.use(express.json());
app.get("/", (req, res) => {
  res.sendFile(__dirname + "/index.html");
});

io.on("connection", (socket) => {
  console.log("a user connected");
  socket.on("chat message", (msg) => {
    io.emit("chat message", msg);
  });
});

server.listen(4000, () => {
  console.log("server is running");
});
export default app;
```

이러한 코드인데 io.on으로 클라이언트로 부터 요청을 전송받아 유저가 연결이 되엇는지 알수있는 코드엿다
socket.on 부분에서 클라이언트에서 보낸 이벤트 "chat message" 에 담긴 정보를 받아 emit 메서드를 통해 모두에게 그메시지 를 전달할수 있다

오늘 처음 배운 내용이지만 공식문서 따라 해보는 것만으로도 재미있엇다 채팅방도 만들수있다고 하니 그런메서드를 추가적으로 찾아보고 타입스크립트에 대해서도 한번 공부해보고 적용해보아야겟음.
