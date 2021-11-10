### 재귀함수

간단정의 ! 문제를 동일한 구조의 더 작은 문제로 나눌 수 있고, 이 작은 문제를 해결함으로써 전체 문제를 해결하는 방법을 재귀(recursion)라고 합니다. 재귀를 사용한 코드는 대부분의 경우 더욱 간결하고, 이해하기 쉽습니다. 그 밖에도 재귀는 알고리즘 문제의 많은 부분을 차지합니다.

### JSON

JSON은 JavaScript Object Notation의 줄임말로, 데이터 교환을 위해 만들어진 객체 형태의 포맷입니다.
객체는 타입 변환을 이용해 String으로 변환할 경우 객체 내용을 포함하지 않습니다. JavaScript에서 객체에 메소드(message.toString())나 형변환(String(message))을 시도하면, [object Object] 라는 결과를 리턴합니다.

이 문제를 해결하는 방법은 객체를 JSON의 형태로 변환하거나 JSON을 객체의 형태로 변환하는 방법입니다. 이를 위한 메소드는 다음과 같습니다.
. JSON.stringify : Object type을 JSON으로 변환합니다.
. JSON.parse : JSON을 Object type으로 변환합니다.

```js
let transferableMessage = JSON.stringify(message);
console.log(transferableMessage); // `{"sender":"김코딩","receiver":"박해커","message":"해커야 오늘 저녁 같이 먹을래?","createdAt":"2021-01-12 10:10:10"}`
console.log(typeof transferableMessage); // `string`
```

stringify하는 이 과정을 직렬화(serialize)한다고 합니다.

JSON으로 변환된 객체의 타입은 문자열입니다. 발신자는 객체를 직렬화한 문자열을 누군가에게 객체의 내용을 보낼 수 있습니다. 그렇다면 수신자는 이 문자열 메시지를 어떻게 다시 객체의 형태로 만들 수 있을까요? JSON.stringify와 정반대의 작업을 수행을 하는 메소드 JSON.parse 를 사용할 수 있습니다.

```js
let packet = `{"sender":"김코딩","receiver":"박해커","message":"해커야 오늘 저녁 같이 먹을래?","createdAt":"2021-01-12 10:10:10"}`;

let obj = JSON.parse(packet);
console.log(obj);
/*
 * {
 * sender: "김코딩",
 * receiver: "박해커",
 * message: "해커야 오늘 저녁 같이 먹을래?",
 * createdAt: "2021-01-12 10:10:10"
 * }
 */
console.log(typeof obj);
// `object`
```

JSON.parse를 적용하는 이 과정을 역직렬화(deserialize)한다고 합니다.

#### JSON의기본규칙

얼핏보기에는 자바스크립트와 다를바가 없지만 미묘하게 다르다
자바스크립트 객체는 키 = 큰따옴표 없이 사용가능
문자열값 문자열 값은 어떠한 형태의 따옴표도 사용가능

JSON 은 두경우 모두 반드시 큰따옴표를 붙혀야함

#### DOM 복습

금일 스프린트를 진행하면서 다시한번 DOM 복습을 진행하였습니다.
CREATE - createElement
APPEND - append, appendChild
READ - querySelector, querySelectorAll
UPDATE - textContent, classList.add
DELETE - remove, removeChild

#### Node와 Element 의차이점

Node와 Element
Node는 태그 노드와 텍스트 노드 전체를 가리키고, Element는 텍스트 노드를 제외하고, 흔히 생각하는 태그(<a>같은)만 가리킵니다. 따라서 태그만 검색하고 싶을 때는 Element가 붙은 메소드를 선택해야합니다.

#### remove()와 removechild의 차이

remove() 는 노드를 메모리에서 삭제하고 종료합니다. 하는데 반해, 반면 removeChild()는 노드를 삭제하는 것이 아닙니다. 메모리에 해당 노드는 그대로 존재하며, 부모 노드와의 부모-자식관계를 끊어 DOM 트리에서 해제하는 것입니다
