### Promise

Promise 객체는 비동기 작업이 맞이할 미래의 완료 또는 실패와 그 결과 값을 나타냅니다.
Promise는 프로미스가 생성될 때 꼭 알 수 있지는 않은 값을 위한 대리자로, 비동기 연산이 종료된 이후의 결과값이나 실패 이유를 처리하기 위한 처리기를 연결할 수 있도록 합니다. 프로미스를 사용하면 비동기 메서드에서 마치 동기 메서드처럼 값을 반환할 수 있습니다. 다만 최종 결과를 반환하지는 않고, 대신 프로미스를 반환해서 미래의 어떤 시점에 결과를 제공합니다.

Promise는 다음 중 하나의 상태를 가집니다.

대기(pending): 이행하거나 거부되지 않은 초기 상태.
이행(fulfilled): 연산이 성공적으로 완료됨.
거부(rejected): 연산이 실패함.

### Node.js

Node.js 에서는 자바스크립트 코드 가장 상단에 require 구문을 이용하여 다른 파일을 불러옵니다

```js
const fs = require("fs"); // 파일 시스템 모듈을 불러옵니다
const dns = require("dns"); // DNS 모듈을 불러옵니다
```

### fetch

fetch API는 위와 같이, 특정 URL로부터 정보를 받아오는 역할을 합니다. 이 과정이 비동기로 이루어지기 때문에, 경우에 따라 다소 시간이 걸릴 수 있습니다. 이렇게 시간이 소요되는 작업을 요구할 경우에는 blocking이 발생하면 안 되므로, 특정 DOM에 정보가 표시될 때까지 로딩 창을 대신 띄우는 경우도 있습니다.

```js
et url =
  "https://v1.nocodeapi.com/codestates/google_sheets/YbFMAAgOPgIwEXUU?tabId=최신뉴스";
fetch(url)
  .then((response) => response.json())
  .then((json) => console.log(json))
  .catch((error) => console.log(error));
```
