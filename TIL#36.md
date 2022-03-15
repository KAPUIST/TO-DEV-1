타입스크립트를 조금 끄적여 보앗다 새로운 스택이라 배우는데 재미가 있습니다!

#### 타입스크립트를 사용하는이유

자바스크립트가 유명한건 엄격한 규칙이 없기때문이고, 사용하기 쉽고 우리가 원하는 방향으로 수정하기도 편하기때문
그러나 큰 프로젝트를 한다거나 팀으로 일을한다거나 버그를 최소화 하고싶을때 자바스크립트의 장점은 단점이 되게 됩니다

그래서 타입스크립트가 탄생하게 되엇음!

#### 장점 첫번째

```js
const name = "Taegwon",
  age = 27,
  gender = "male";

const sayHi = (name, age, gender) => {
  console.log(`Hello ${name}, you are ${age}, you are a ${gender}`);
};
sayHi(name, age);
export {};
```

이러한 코드에서 원래 자바스크립트 엿다면
Hello Taegwon, you are 27, you are a undefined
라는 결과를 돌려주게 됩니다 gender 받지 못햇기 때문!
하지만 typescript에서는 이는 잘못되엇다 오류를 반환하게 됩니다.

Expected 3 arguments, but got 2.

바로 이러한 오류 입니다.
3개의 아규먼트를 받을거라 예상햇지만 2개밖에 받지 못햇다는 오류를 돌려주게됩니다! 자바스크립트엿다면 그냥 돌아갔을터!

만약 자바스크립트와 같은 내용을 받아보고싶다면 gender를 옵셔널 하게 바꾸어주면됩니다! 뒤에 ? 를 붙혀서 말이죠

```js
const sayHi = (name, age, gender?) => {
  console.log(`Hello ${name}, you are ${age}, you are a ${gender}`);
};
```

이렇게 하게되면 타입스크립트에서도 젠더 아규먼트가 빠져도 정상작동 한다!

#### 장점 두번째

```js
const sayHi = (name: string, age: number, gender: string) => {
  console.log(`Hello ${name}, you are ${age}, you are a ${gender}`);
};
sayHi("Taegwon", 27, "male");
export {};
```

이번엔 함수에 타입을 적어 주엇습니다 만약 SayHi("Taegwon", "27", "male");

넘버 타입이 들어가야하지만 스트링 타입이 들어가게 되면 오류를 되돌려준다.

#### 더세세하게

```js
interface Human {
  name: string;
  age: number;
  gender: string;
}

const person = {
  name: "taegwon",
  age: 22,
  gender: "male",
};

const sayHi = (person: Human): string => {
  return `Hello ${person.name}, you are ${person.age}, you are a ${person.gender}`;
};
console.log(sayHi(person));
export {};
```

와우 엄청나게 타입을 엄격하게 대하고있음을 알수있고 어떤식으로 값을 돌려줄지 어떠한 값들이 예측이가능하다 아 interface는 js에 관여하지않는다.
