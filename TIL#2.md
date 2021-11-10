# TO DEV

## \_TIL #2

### 문자열 string method

- str[4]
  문자열 index로 접근은 가능하지만 사용할순없음 read only + 연산자 사용가능 - 불가
  'code' + 'states' = 'code states'
  '1'+7 = '17'

#### str.concat

```js
onst str1 = 'Hello';
const str2 = 'World';

console.log(str1.concat(' ', str2));
// expected output: "Hello World"

console.log(str2.concat(', ', str1));
// expected output: "World, Hello"
```

- length 길이

#### str.indexof(serchvalue)

- argument : 찾고자 하는 문자열
- return value : 처음부터 일치하는 index , 찾고자하는 문자열이 없으면 -1
- lastindexof :문자열 뒤에서 부터 찾음

```js
"Blue Whale".indexOf("Blue"); // 0
"Blue Whale".indexOf("blue"); // -1
"Blue Whale".indexOf("Whale"); // 5
"Blue Whale Whale".indexOf("Blue"); // 5

"canal".lastindexOf("a"); // 3
```

#### see more : str.includes (serchvalue)

includes() 메서드는 하나의 문자열이 다른 문자열에 포함되어 있는지를 판별하고, 결과를 true 또는 false 로 반환합니다.

```js
var str = "To be, or not to be, that is the question.";

console.log(str.includes("To be")); // true
console.log(str.includes("question")); // true
console.log(str.includes("nonexistent")); // false
console.log(str.includes("To be", 1)); // false
console.log(str.includes("TO BE")); // false
```

#### str.split(seperator) 분리의기준이 되는 문자열이 들어감

```js
var str = "hello from the other side";

console.log(str.split(" "));
["hello", "from", "the", "other", "side"];
//공백을 자른것 (배열)
```

##### csv 형식을 처리할때 유용

줄바꿈문자를 분석할때는 csv.split('\n')

```js
let csv =`연도,제조사,모델,설명,가격
1997,Ford,E350,"ac, abs, moon",3000.00
1999,Chevy,"Venture ""Extended Edition""","",4900.00
1999,Chevy,"Venture ""Extended Edition, Very Large""",,5000.00
1996,Jeep,Grand Cherokee,"MUST SELL!
air, moon roof, loaded",4799.00`;
>>>>>
csv.split(',')
(26) ['연도', '제조사', '모델', '설명', '가격\n1997', 'Ford', 'E350', '"ac', ' abs', ' moon"', '3000.00\n1999', 'Chevy', '"Venture ""Extended Edition"""', '""', '4900.00\n1999', 'Chevy', '"Venture ""Extended Edition', ' Very Large"""', '', '5000.00\n1996', 'Jeep', 'Grand Cherokee', '"MUST SELL!\nair', ' moon roof', ' loaded"', '4799.00']
csv.split('\n')
(6) ['연도,제조사,모델,설명,가격', '1997,Ford,E350,"ac, abs, moon",3000.00', '1999,Chevy,"Venture ""Extended Edition""","",4900.00', '1999,Chevy,"Venture ""Extended Edition, Very Large""",,5000.00', '1996,Jeep,Grand Cherokee,"MUST SELL!', 'air, moon roof, loaded",4799.00']0:

"연도,제조사,모델,설명,가격"1: "1997,Ford,E350,\"ac, abs, moon\",3000.00"2: "1999,Chevy,\"Venture \"\"Extended Edition\"\"\",\"\",4900.00"3: "1999,Chevy,\"Venture \"\"

let lines = csv.split('\n')

lines[1]
'1997,Ford,E350,"ac, abs, moon",3000.00'
lines[0].split(',')
(5) ['연도', '제조사', '모델', '설명', '가격']
```

#### str.substring(star, end) slice많이씀

0 3 이면 0 1 2 만가져옴

```js
var str = 'abcdefghij';
console.log(str.substring(0,3));
console.log(str.substring(3,0));
console.log(str.substring(1,4)); 1 2 3 만가져옴
console.log(str.substring(-1,4)); 음수는 0으로 취급
console.log(str.substring(0,20));
```

#### str.toUpperCase , str.toLowerCase

string method 는 immutable 원본이 변하지않음

```js
let word = "hello";
word.toUpperCase();
("HELLO");
word;
("hello");
```

#### Template literals

템플릿 리터럴에서는 아래와 같이 $와 중괄호{}를 사용하여 표현식을 표기할 수 있습니다.

```js
let a = 20;
let b = 8;
let c = "자바스크립트";
let str = `저는 ${a + b}살이고 ${c}를 좋아합니다.`;
console.log(str); //저는 28살이고 자바스크립트를 좋아합니다.
```

위 처럼 + 연산자로 문자열을 연결해주는 것보다 가독성이 더 좋습니다.

#### Math.abs

절대값을 구할때 사용한다

```js
//Math.abs(숫자);
Math.abs(5); // 5
Math.abs(-5); // 5
Math.abs([2]); // 2
```

#### parseInt()

string을 정수로 변환한 값을 리턴합니다.

만약, string의 첫 글자를 정수로 변경할 수 없으면 NaN(Not a Number) 값을 리턴합니다.

```js
parseInt("10"); // 10
문자열 "10"을 숫자로 변환하여 정수 10을 리턴합니다.
parseInt("-10"); // -10
문자열 "-10"을 숫자로 변환하여 정수 음수 -10을 리턴합니다.
parseInt("10.9"); // 10
문자열 타입의 실수값은 소수점을 제거한 후, 정수값만 리턴합니다.
parseInt(10); // 10
파라미터로 문자열이 아닌 다른 타입의 값이 전달되면,
파라미터를 문자열로 변환하여 처리합니다.
```

#### parseFloat()

파라미터로 입력받은 문자열을 실수로 변환 한 값을 리턴합니다.
파라미터로 입력받은 문자열을 실수로 변환할 수 없는 경우에는 NaN (Not a Number) 값을 리턴합니다.
첫 글자가 숫자로 변환할 수 있는 값(숫자(0~9), 기호(+, -), 소수점(.), 지수)이 아닌 경우, NaN을 리턴합니다.
첫 글자 이후에 숫자로 변환할 수 없는 값이 오는 경우, 그 이후 값들은 무시합니다.

```js
parseFloat("10"); // 10
입력받은 문자열에 소수점이하 자리가 없으므로, 그대로 정수 10을 리턴합니다.
parseFloat("-10"); // -10
음수 값도 변환할 수 있습니다.
parseFloat("10.9"); // 10.9
문자열을 실수로 변환하여 실수를 리턴하였습니다.
parseFloat(10.9); // 10.9
파라미터로 문자열이 전달되지 않고, 다른 타입의 값이 전달되면
전달된 파라미터를 문자열로 변환한 후, 실수로 변환하여 그 값을 리턴합니다.
```

#### trim

문자열 양끝의 공백을 제거.

```js
var orig = "   foo  ";
console.log(orig.trim()); // 'foo'
```

#### match()

해당 문자열.match('찾을 단어')
// match()함수는 인자에 포함된 문자를 찾으면 이를 반환함

```js
if (str.match("red") === "red") {
  console.log("Okay");
}
var str = "red is impressive.";

str.match("red");
// red가 있으므로 red를 출력함
```

#### replace

str_text.replace("찾을 문자열", "변경할 문자열")

```js
ar test = '가나다라 마바사 가나';
var result = test.replace('가', '나');

console.log(result);
 나나다라 마바사 가나

// 출력 결과는 맨 앞의 "가"는 "나"로 변경됨
```

#### 정규 표현 str_text.replace(/찾을 문자열/gi, "변경할 문자열")

이번에는 정규표현식을 알아봅니다. 정규표현식(Regular Expression) 정해진 규칙을 사용해 모든 문자를 변환할 수도... 숫자만 변환하거나 맨 처음 또는 맨 뒤만 변환할 수도 있습니다. 매우 강력한 기능을 가지고 있죠. 그럼 간단한 예제를 보세요.

```js
var test = "가나다라 마바사 가나";
var result = test.replace( /가/gi, '나');

console.log(result);

나나다라 마바사 나나
// 포함된 모든 "가"는 "나"로 변환되었음
```
