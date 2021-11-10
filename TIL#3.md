# TO DEV

## \_TIL #3

#### 반복문

반복할 조건을 초기화, 조건문, 증감문 순으로 넣어준다 (for, while)
일반적으로 반복 횟수가 예측 가능할 때는 for 문을 사용하는 것이 가독성이 더 좋고, 반복 횟수를 예측할 수 없으면 while 문을 사용하는 것이 더 적합한 경우가 많다.

```js
let sum = 1;
for(let n =2; n <= 4; n = n +1){
    sum = sum + n;
}
console.log(sum)


/ 로그인 성공 여부를 보관하는 변수
var login = false;

// 최대 다섯 번의 기회를 준다
for (var i = 0; i < 5; i++) {
  // 아이디와 비밀번호를 입력 받는다
  var id = window.prompt("아이디를 입력하세요");
  var password = window.prompt("비밀번호를 입력하세요");

  if (id === 'codeit' && password === '4321') {
    console.log('환영합니다. ' + id + '님.');
    login = true;
    break;
  } else {
    console.log('아이디와 비밀번호가 일치하지 않습니다.');
  }
```

#### while 구문

while 문 같은경우에는 초기화식 증감문은 따로 적고 , 조건식 만 괄호 안에 넣어 줍니다.

```js
// 로그인 성공 여부를 보관하는 변수
var login = false;

// 로그인에 성공할 때까지 반복
while (!login) {
  // 아이디와 비밀번호를 입력 받는다
  var id = window.prompt("아이디를 입력하세요");
  var password = window.prompt("비밀번호를 입력하세요");

  if (id === "codeit" && password === "4321") {
    console.log("환영합니다. " + id + "님.");
    login = true;
  } else {
    console.log("아이디와 비밀번호가 일치하지 않습니다.");
  }
}
```

#### 이중포문

```js
function makePermutations(str) {
  // 문자열 순서대로 문자갯수만큼
  // 글자수가 몇개인지 = str.length 길이
  // 문자를 만들어 리턴
  let result = "";
  for (let i = 0; i < str.length; i++) {
    for (let j = 0; j < str.length; j++) {
      result = result + `${str[i]}${str[j]},`;
    }
  }
  return result.slice(0, result.length - 1);
}
```

### factorial

팩토리얼의 정의

1부터 어떤 양의 정수 n까지의 정수를 모두 곱한 것을 말한다.

표기법은 n!

```js
//팩토리얼

function factorial(n) {
  let result = 1;
  for (let i = 1; i <= n; i++) {
    result = result * i;
  }

  return result;
}
```

### str.repeat(count);

count
문자열을 반복할 횟수. 0과 양의 무한대 사이의 정수([0, +∞)).

```js
function repeatString(str, num) {
  // TODO: 여기에 코드를 작성합니다.
  let result = "";
  for (let i = 1; i <= num; i++) {
    result = str.repeat(i);
  }
  return result;
}
```

이게왜?

```js
function sumTo(num) {
  // TODO: 여기에 코드를 작성합니다.
  let sum = 0;
  for (let i = 0; i <= num; i++) {
    sum = sum + i;
  }
  return sum;
}
```

```js
function makeMultiplesOfDigit2(num1, num2) {
  // TODO: 여기에 코드를 작성합니다. //
  let result = 0;
  let big = num2;
  let small = num1;
  if (num1 > num2) {
    big = num1;
    small = num2;
  }
  for (let i = small; i <= big; i++) {
    if (i % 2 === 0 && i !== 0) {
      result = result + 1;
    }
  }
  return result;
}
```

#### absNum = Math.abs(num);

Math.abs() 함수는 주어진 숫자의 절대값을 반환합니다. x가 양수이거나 0이라면 x를 리턴하고, x가 음수라면 x의 반대값, 즉 양수를 반환합니다

```js
Math.abs("-1"); // 1
Math.abs(-2); // 2
Math.abs(null); // 0
Math.abs(""); // 0
Math.abs([]); // 0
Math.abs([2]); // 2
```

#### sort()

sort() 메서드를 이용해 배열을 정렬할 수 있으며, sort() 메서드는 모든 것들을 문자열로 변환한 다음 기본적으로 사전순으로 정렬한다. 다음 예제를 보자.

```js
var arr = [2, 1, 15];
arr.sort();
console.log(arr);               // [1, 15, 2]

숫자를 기준으로 정렬하려면 직접 정의한 비교 함수를 전달할 필요가 있다. 다음 예제를 보자.

function compare(a,b){
    if (a>b) return 1
    else if (b>a) return -1
    else return 0
}
var arr = [2, 1, 15];
arr.sort(compare);
console.log(arr);               // [1, 2, 15]
```

#### Math.min Math.max

Math.min() 함수는 주어진 숫자들 중 가장 작은 값을 반환합니다.

```JS
math.min
var x = 10, y = -20;
var z = Math.min(x, y);


math.max
Math.max(10, 20);   //  20
Math.max(-10, -20); // -10
Math.max(-10, 20);  //  20
```
