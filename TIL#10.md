# TO DEV TIL
### react
JSX는 JavaScript XML의 줄임말로 문자열도 아니고 HTML도 아닙니다.
React에서 UI를 구성할 때 사용하는 문법으로 JavaScript를 확장한 문법입니다.
React에서는 DOM과 다르게 CSS, JSX 문법만을 가지고 웹 애플리케이션을 개발할 수 있습니다

React 에서 여러 개의 HTML 엘리먼트를 표시할 때는 "map()" 함수를 사용합니다.

map 함수를 사용할 때는 반드시 "key" JSX 속성을 넣어야합니다.
"key" JSX 속성을 넣지 않으면 리스트의 각 항목에 key를 넣어야 한다는 경고가 표시됩니다.
##### babel
JSX는 JavaScript가 확장된 문법이지만, 브라우저가 바로 실행할 수 있는 JavaScript 코드가 아닙니다. 
이해할 수 있는 JavaScript 코드로 변환을 해주어야 합니다.
이때 이용하는 것이 바로 “Babel”입니다. Babel은 JSX를 브라우저가 이해할 수 있는 JavaScript로 컴파일합니다. 컴파일 후, JavaScript를 브라우저가 읽고 화면에 렌더링할 수 있습니다.

### Component
정의
하나의 기능을 구현하기 위한 여러 종류의 코드 묶음
UI를 구성하는 

### React Router
React Router의 주요 컴포넌트는 크게 3가지로 나눌 수 있습니다. 라우터 역할을 하는 BrowserRouter, 경로를 매칭해주는 Switch 와 Route, 그리고 경로를 변경하는 역할을 하는 Link 입니다.
이컴포넌트들을 사용하기위해서는 모듈을 불러와야합니다
import{ BrowserRouter,Switch,Route,Link}from "react-router-dom" 

### useState 간단 사용법
let [글제목,글제목 변경] = useState(['남자 코트 추천','강남 우동 맛집'])
state에 데이터를 저장해놓는 이유는 웹이 App처럼 동작하게 만들고 싶어서
state는 변경되면 html이 자동으로 재렌더링됩니다 결과는 html이 새로고침이 필요없음 자주바뀌는 중요한데이터는 변수말고 state를 사용합니다 



### 메소드 
arr.flat  
```js
const arr1 = [1, 2, [3, 4]];
arr1.flat();
// [1, 2, 3, 4]

const arr2 = [1, 2, [3, 4, [5, 6]]];
arr2.flat();
// [1, 2, 3, 4, [5, 6]]

const arr3 = [1, 2, [3, 4, [5, 6]]];
arr3.flat(2);
// [1, 2, 3, 4, 5, 6]

const arr4 = [1, 2, [3, 4, [5, 6, [7, 8, [9, 10]]]]];
arr4.flat(Infinity);
// [1, 2, 3, 4, 5, 6, 7, 8, 9, 
```