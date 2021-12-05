### CSS 방법론들의 특징 , 장단점 리뷰!

1. CSS

- 특징 : 기본적인 스타일링 방법
- 단점 : 일관된 패턴을 가지기 어려움, !import의 남용

2. SASS(preprocessor)

- 특징 : 프로그래밍 방법론을 도입하여, 컴파일된 CSS를 만들어내는 전처리기
- 장점 : 변수/함수/상속 개념을 활용하여 재사용 가능 CSS 구조화
- 단점 : 전처리 과정이 필요하고 디버깅에 어려움이 있으며 컴파일한 CSS 파일이 거대해짐

3. BEM

- 특징 : CSS 클래스명 작성에 일관된 패턴을 강제하는 방법론
- 장점 : 네이밍으로 문제해결, 전처리 과정이 불필요함
- 단점 : 선택자 이름이 너무 장황해지고, 클래스 목록이 너무 많아짐

4. Styled-Component (CSS-in-JS)

- 특징 : 컴포넌트 기반으로 CSS를 작성할수 있게 도와주는 라이브러리
- 장점 : CSS를 컴포넌트 안으로 캡슐화, 네이밍이나 최적화를 신경쓸 필요가 없음
- 단점 : 빠른페이지 로드에 불리함

### React 상태관리 Redux

#### 배울내용

- 상태관리 라이브러리가 왜필요한지 알아야한다
- Redux에서 사용하는 Action, Reducer그리고 Store의 의미와 특징을 이해할수있다
- Redux의 3가지원칙이 무엇이며, 주요개념과 어떻게 연결되는지 이해할수있어야한다.
- Presentational 컴포넌트와 Container 컴포넌트의 개념을 이해할수있다
- Redux hooks(useSelector, useDispatch)를 사용해 Store를 업데이트 할수있다.

### 리덕스의 세가지원칙

1. Single source of truth(동일한데이터는 항상 같은곳에서 데이터를 가지고온다)
2. State is read-only(읽기만 할수있다)
3. Changes are made with pure functions(변경은 순수함수로만 가능 (Reducer))

#### Redux의 기본개념: Store

상태가 관리되는 오직 하나의 공간

#### Redux의 기본개념: Action

액션은 자바스키립트객체입니다
객체안에 타입을 비롯한 다양한 데이터를 담고 이객체는 스토어에게 우리앱의 데이터를 운반해주는 역활을 합니다

Redux의 action은 자바스크립트 객체이다. 유형 및 옵션 페이로드가 있습니다. 이 유형을 작업 유형이라고도 합니다. 유형이 문자열 리터럴인 반면 페이로드가 문자열에서 객체까지의 모든 것이 될 수 있습니다

작업을 실행하는 것을 Redux에서 디스패치라고 합니다. Redux 저장소의 상태를 변경하는 작업을 보낼 수 있습니다. 상태를 변경하려는 경우에만 작업을 발송합니다. 작업 발송은 보기에서 트리거될 수 있습니다. HTML 버튼을 클릭하는 것만큼 간단할 수 있습니다. 또한 Redux 작업의 페이로드는 필수 사항이 아닙니다. 작업 유형만 있는 작업을 정의할 수 있습니다. 결국, 동작이 디스패치되면 Redux의 모든 리듀서를 거치게 된다.
코드 예시

```js
{
    type:'ORDER'.
    drink:{
        menu:"Americano",
        size:"Grande",
        iced:false
    }
}
```

#### Redux의 기본개념: Reducer

현재 상태와 Action을 이용해서 다음상태를 만들어냄

Action => Reducer => store(New State)

Action 객체는 Dispatch 에게 전달되고 Dispatch는 Reducer를 호출해서 새로운 state 생성

간단히 설명하면 Dispatch 는 Action 객체가 Dispatch라는 메소드를 전달되고 Dispatch가 Reducer를 호출하고 새로운 State 값을 만들어낸다

Reducer는 순수한 함수이다. 입력이 동일하게 유지될 때 항상 동일한 출력을 생성합니다. 부작용이 없dmsl 입출력 작업일 뿐이다.
일단 받아들이고 코드를 직접짜봅시다

```js
function(state, action) {
  state.push(action.todo);
  return state;


  function reducer(state, action) {
  return state.concat(action.todo);
}
}
```

#### Redux의 장점

1. 상태를 예측가능하게 만들어 준다.
   Reducer라는게 순수함수기때문에 예측이쉽다
2. 유지보수

3. 디버깅에 유리하다(action과state log 기록시)
4. 테스트를 붙이기 쉽다.

##### 객체 얕은 복사

```js
let a = { codestates: "im good", code: "not good" };
let b = { hansomeguy: "VENOM" };

console.log({ ...a, ...b });
// { codestates: "im good", code: "not good",hansomeguy: "VENOM"}
```
