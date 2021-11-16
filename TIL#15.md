### 콜백함수 리뷰

- 다른 함수(a)의 전달인자로 넘겨주는 함수(b)

- parameter를 넘겨받는 함수 (a)는 콜백함수(b)를 필요에따라 즉시실행 할수도 있고, 아니면 나중에 실핼할수도있다
  a(b)

### 비동기 함수 전달패턴

callback 패턴

```js
let request = "caffelatte";
orderCoffeeAsync(request, function (response) {
  drink(response);
});
```

이벤트 등록패턴

```js
let request = "caffelatte";
orderCoffeeAsync(request).onready = function (response) {
  drink(response);
};
```

### 비동기의 주요사례

1. DOM Element의 이벤트 핸들러

- 마우스, 키보드 입력
- 페이지 로딩

2. 타이머

- 타이머 API
- 애니메이션 API

3. 서버에 자원 요청및 응답

- fetch APi
- Ajax

### 비동기 자바스크립트
