# TO DEV

## \_TIL #1

변수(variable)란 데이터보관 이라고 할수있다 보관함의크기는 모두 동일하고 각보관함의 이름을 변수라고 칭할수가 있다 변수를 통해서 보관된 데이터를 꺼내어 사용할수있다.

(마치 태그 같다)

- 먼저 변수 선언을하고 let...
- 보관함에 데이터를 할당 시킨다 age...
- 선언과 할당은 동시에 이루어질수있다.
- = 는 "같다"라는 의미가아닌 할당연산자라 한다

코드의 각 한줄을 표현식(expression)이라고 부른다

선언과 할당을 해보았다

```js
 let iphone;
 iphone = 11pro;
 consloe.log(iphone)
```

식당에서 음식을 팔았을때 가격을 코드로 만들어보자

```js
let mandu = 9000;
sell = 5; // 판매된개수
console.log(mandu * sell);
```

할당이 없는 변수가 있다면 그의미는 undefined 정의되지 않았다.

## 타입

- 원시 자료형 string , number , boolean , undefined

이런타입들이 여러가지 섞여있는것을(compound)타입이라한다

```js
let cat = {
  name: "moon",
  age: 10,
  isanimal: true,
};
console.log(cat);
```

변수에 값이 없다는 뜻인 undefinre도 타입이다.
데이터 타입을 확인하고 싶을때 javascript 에서는 typeof를 사용한다.

```js
let cat = (age = 10);
console.log(typeof cat);
```

문자열은 "number"를 리턴하게된다.

# = , == , === 차이는?

= (value값)
예 : number = 2
== (value와value를비교)
예:a = 10 , b = 5라고할때 a == b 는 false
=== (value와datatype을비교)
예:a=10이라고 할때, a === 10은 ture, a==="10"은false

== / !=(같다/같지않다)
익숙한 연산자인데 === / !== 이건 뭐지?

=== / !== 은 엄격한 비교이다.

'엄격하게'의 의미는 변수 타입까지 고려한다는 것입니다.

# 원시 자료형이란?

- 자바스크립트에서 원시 타입의 데이터(primitive data types; 원시 자료형)는 객체가 아니면서 method를 가지지 않는 6가지의 타입
  string, number, bigint, boolean, undefined, symbol, (null)

- 원시 자료형의 보관함인 변수에는 하나의 데이터만 담을 수 있습니다.

- 원시 자료형이 담기는 보관함의 크기는 고정하는 것이 합당합니다. 어느정도 일정한 크기의 데이터가 온다고 예상할 수 있기 때문입니다.

# 참조 자료형이란?

- 원시 자료형이 아닌 모든 것은 참조 자료형. 배열([])과 객체({}), 함수(function(){})가 대표적
- 참조 자료형을 변수에 할당할 때는 변수에 값이 아닌 주소를 저장합니다.
- 하나의 주제는 있지만 분명 서로 다르고, 여러 개의 데이터를 가지고 있다.

# 둘의 특징을 정리하자면?

- 원시 자료형이 할당될 때에는 변수에 값(value) 자체가 담기고, 참조 자료형이 할당될 때는 보관함의 주소(reference)가 담깁니다.
- 그래서 참조 자료형은 기존에 고정된 크기의 보관함이 아니라, 동적으로 크기가 변하는 특별한 보관함을 사용할 수 있습니다.

원시 타입 데이터는 각 변수간에 데이터를 복사할 경우, 데이터 값이 복사되기 때문에 기존의 데이터에 영향이 가지 않는다

```js
let a = 1;
b = a; //데이터를 복사할 경우
b = 2;
a; //1, 기존의 데이터에 영향이 가지 않는다
```

참조 타입 데이터는 주소를 복사한다.
그렇기 때문에 복사한 데이터에서 원소를 변경하면, 주소안에 있는 데이터가 변경되는 것이기 때문에 기존의 데이터에도 영향이 간다.

```js
let e = [10, 20];
let f = e;
f[0] = 50;
console.log(e);
```

# 함수funtion

##### 함수 Intro

- 함수가 "작은 기능의 단위"라는 것을 이해할 수 있다.
- 함수 선언을 위해 필요한 keyword, name, parameter, body에 대해 이해할 수 있다.
- 함수 선언과 호출의 기초적인 작동 원리를 이해할 수 있다.
- 함수가 선언되어 함수 표현식이 변수에 담기는 과정을 설명할 수 있다.
- 함수의 결과값이 변수에 할당되어 담기는 과정을 설명할 수 있다.

##### 함수 기초, 함수 실습

- 함수의 호출과 리턴에 대해서 이해하고, 실제 코드로 작성하여 활용할 수 있다.
- 함수 그 자체(func)와, 함수의 호출(func())를 구분하여 사용할 수 있다.
- 매개변수(parameter)와 전달인자(argument)를 구분하여 사용할 수 있다.
- 같은 기능을 하는 함수를 선언식, 표현식, 화살표 함수로 바꾸어 표현할 수 있다.

함수의 구분 keyword, name, parameter, body
함수란 코드의 묶음 버튼처럼 필요할때마다 사용할수있다.
함수는 구체적인 입력값과 출력값을 가질수있다.
함수는 호출후에는 반드시 돌아온다.

## how to use?

함수는 특별한공간에저장되며 언제든 다시사용할수있고 이를 함수의 호출이라고함
함수가 호출되면 특별 저장공간에 있는 함수의 코드가 조회된다??

```js
//함수선언식
function squre(base, height) {
  let squre = base * height;
  return squre;
}
console.log(squre(5, 4));
//함수 표현식
const squre = function (base, height) {
  let squre = base * height;
  return squre;
};
console.log(squre(4, 4));
//화살표 함수
const squre = (base, height) => {
  let squre = base * height;
  return squre;
};
console.log(squre(3, 4));

//짧게쓴 화살표 함수
const squre = (base, height) => base * height;
console.log(squre(3 * 3));
```

## 구글링 팁 !

- 앞에 mdn을 붙혀 검색해본다 어려울시 영어로 javascript 와함께 검색
  -ex how to convert to string in java script

## 논리 연산자

- && AND 라는 뜻을 가지고있음.
- || OR 이라는 뜻을 가지고있음.
- ! NOT이라는 듰을 가지고 있음.

기억해야할 falsy 값

- if (false)
- if(null)
- if(undefined)
- if(0)
- if(NaN)
- if('') 빈스트링 아무런 값이없음.

## 다시한번 써보는 어려웟던 코드

```js
if((num1, num2 < 9) && (num1 %2 == 0 || num2 %2 ==0) )// 괄호해야하는지 몰랏었다.{
  return true
}else
return false

even = num %2 ==0

```

새로배운 Math.floor 넘버값의 가장큰 정수만 가져온다.
