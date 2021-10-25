# TO DEV TIL

### 배열문제 
...splice() 제거를 시작할 인자 , 제거할개수 , 추가할 내용
...join() 스플릿의 반대 합쳐줄수있다.

이부분 문제에서 좀헷갈리는 부분이 있어서 이따가 다시봐야겟다.
```js
function getValueOfNthElement(arr, num) {
  if (!arr.length) {
    return 'no name';
  } else if (num > arr.length - 1) {
    return arr[arr.length - 1]['name'];
  } else {
    return arr[num]['name'];
  }
}
```

reduce 란?

### CSS
```css
* {
  box-sizing: border-box;
}
```
모든 요소에 'box-sizing: border-box'를 추가합니다.
```css
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  padding: 0;
}
```
기본 스타일링을  제거하는 css


:hover
부트스트랩
hr




number,string,boolean  과같은 고정된 저장 공간을 차지하는 데이터를 모두원시타입이라한다{primitive type}

배열,객체,함수은  heap이라고 하는 주소저장소에  저장된다 이를 참조 타입 데이터라고 한다

scope 는 영어자체로 범위라는 의미를 가지고 있다 자바스크립트에서도,무언가 제한된 범위를 잘들여다보기위해 사용되는 개념이라고 추측해보자 . 변수들의 유효범위!

scope의 종류
블록스코프, 함수스코프, 화살표 함수는 블록스코프
변수에 접근할 수 있는 범위가 존재합니다. 중괄호(블록) 안쪽에 변수가 선언되었는가, 바깥쪽에 변수가 선언되었는가가 중요합니다. 이 범위를 우리는 스코프라고 부릅니다.'

바깥쪽 스코프에서 선언한 변수는 안쪽 스코프에서 사용 가능합니다.
반면에, 안쪽에서 선언한 변수는 바깥쪽 스코프에서는 사용할 수 없습니다.

특별히 가장 바깥쪽의 스코프는 전역 스코프(Global Scope)라고 부릅니다. 전역의 반대말은 지역(local)으로 전역이 아닌 다른 스코프는 전부 지역 스코프(local scope)입니다.
let , constt, var의 차이
var키워드는 for문이 만들어낸 블록 스코프를 무시하고, 함수스코프만 따른다
블록 단위 스코프를 구분했을때 훨씬 예측 가능한 ㅗ드를 작성할수있는 let 키워드의 사용이 권장 되고있다.
var키워드는 재선언을 해도 아무런 에러도 내지 않지만 , let키워드는 재선언을 방지합니다.
const는 변하지않는값, 즉 상수를 정의할때 사용합니다 const는 값의 재할당이 불가능합니다 값을 재할당 할경우 typeerror를 내므로, 의도치않은 값의 변경을 막을수있다.
```js
오늘 스코프 내용 배우면서 별거 아니지만 이해하기 힘들엇던 코드 다시한번 볼거다
let x = 10;

function add (y) {
  return x + y;
}

function strangeAdd (x) {
  return add(x) + add(x);
}

let result = strangeAdd(5); //30

```


window객체
브라우저에는 window라는 객체가 존재 
브라우저 창을 대표하는객체
var로 선언된 전역변수와 전역 함수가 window 객체에 속함

전역변수는 최소화 하라 
전역변수란 어디서든 접근가능한 변수
편리한 대신 , 다른함수 혹은 로직에 의해 의도되지 않은 변경이 발생할수있음
side effect발생.

'use strict' 는 브라우저가 보다 엄격하게 작동하도록 만들어 줍니다. 앞서 언급한 것처럼 "선언 없는 변수"의 경우도 strict mode는 에러로 판단

### closure
closuere 클로저 는 함수롸 함수가 선언된 어휘적 환경의 조합.
클로저라는 문법이 이해하기 조금 힘든점이 있음  지속적으로 찾아보고 있으나 쉽지는 않다 많은 예시를 보며 익숙해질필요있음.
환경 안에있는 함수가 클로저다 
외부함수에 변수에 접근할수있는 내부함수

클로저 예시 테스트
```js
let outfn = function(){
    let x = 10;
    return a = funtion(y){
        return x+y;
    }
}


let a;
{
    let x = 10;
    a = function(y){
        return x+y;
    }
}



const adder = function(x){
return function(y){
return x+y;
}
}
undefined
const addone = adder(1);
undefined
addone
ƒ (y){
return x+y;
}
addone(3)
4

 /./
 let add = function(x){
     let sum = function(y){
         return x+y
     }
     return sum
 }
```



함수두개 
```js
let x = 10;
function outer (){
    x = 20;
    function inner(){
        x=x+20
    }
    inner();
}
let result = x
```

```js
box.style.displat = isShow ? block : none
box.style.opacity = isshow ? 1:0
box.style.transition ="1s"
box.setAttribut
```

Spread 문법
주로 배열을 풀어서 인자로 전달하거나, 배열을 풀어서 각각의 요소로 넣을 때에 사용합니다.
Rest 문법
파라미터를 배열의 형태로 받아서 사용할 수 있습니다. 파라미터 개수가 가변적일 때 유용합니다.

알아야할것
product
깊은 복사 얕은 복사
화살표 함수에서의 this
유사배열
