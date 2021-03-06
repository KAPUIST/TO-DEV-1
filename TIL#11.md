### TIL #11

그동안 시간이부족해서 작성하지 못한부분이 많은데 다시한번 열심히 공부를 시작해보려고합니다 !! 화이팅!

#### 객체지향 자바스크립트

객체지향 프로그래밍
객체지향 프로그램이란 청사진을 만들고 그청사진을 바탕으로 한 오브젝트를 만드는 프로그래밍 패턴이다!.
앞으로, 그냥 객체가 아닌 "청사진"을 바탕으로 한 객체는 인스턴스 객체(instance object), 줄여서 인스턴스(instance)라고 부르겠습니다. 청사진은 클래스(class)라고 부릅시다.

```js
function(Car(color))

let avante = new Car
```

클래스를 그냥 함수로 정의하면, 일반적인 다른 함수와 어떻게 구분하냐고요? 클래스를 만드는 암묵적인 규칙으로, 보통 클래스는 대문자, 그리고 일반명사로 만듭니다.
따라서 일반적인 함수를 만들 때에는, 적절한 동사를 포함하고, 소문자로 시작하도록 만들면 좋습니다.

최근 ES6문법

```js
class Car{
    constructor(brand,name,color)
}
```

여기서 보이는 함수는, 객체지향 프로그래밍에서 생성자(constructor) 함수라고 부릅니다. 인스턴스가 만들어질 때 실행되는 코드죠.

참고로, 생성자 함수는 return값을 만들지 않습니다.

##### 메소드 정의

ES6문법

```js
class Car {
    constructor(brand,name,color){ 생략}
    refuel(){

    }
    drive(){

    }
}
생성자 함수와 함께 클래스 안쪽에 정의합니다.
```

#### new

new 연산자는 사용자 정의 객체 타입 또는 내장 객체 타입의 인스턴스를 생성한다.

```js
function Car(make, model, year) {
  this.make = make;
  this.model = model;
  this.year = year;
}

const car1 = new Car("Eagle", "Talon TSi", 1993);

console.log(car1.make);
// expected output: "Eagle"
```

#### 객체지향 프로그래밍

Must know concepts
질문
추상화와 캡슐화는 어떻게 다른가요?
인터페이스(Interface)란 무엇일까요?
JavaScript에서 class 키워드를 사용하면, 메소드의 은닉이 가능한가요?

#### OOP

OOP는 프로그램 설계 철학 중 하나입니다. OOP는 객체로 그룹화됩니다. 이 객체는 한번 만들고 나면, 메모리상에서 반환되기 전까지 객체 내의 모든 것이 유지됩니다.

oop 의 4가지 기본적인 컨셉으로
. Encapsulation(캡슐화)
. Inheritance(상속)
. Abstraction(추상화)
. Polymorphism(다형성)

##### 캡슐화(ENCAPSULATION)

. 캡슐화는 내부 구현에 대해 유연함을 제공해 주는 기법이다.
. 객체가 내부적으로 기능을 어떻게 구현했는지 감추는 것
. 변경 가능성이 높은 부분은 내부에 숨기고 외부에는 상대적으로 안정적인 부분만 공개함으로써 변경의 여파를 통제한다.
. 변경될 가능성이 높은 부분을 구현이라고 하고 상대적으로 안정적인 부분을 인터페이스라고 한다.
. 외부에 영향을 주지 않고 객체 내부의 구현을 변경할 수 있게 함
. 느슨한 결함 (Loose coupling)에 유리 : 언제든지구현을 수정할수있음

##### 추상화(Abstraction)

. 내부구현은 아주 복잡한데 실제로 노출되는 부분은 되게 단순하게 만든다는 개념

추상화는 캡슐화와 비교해서 종종 헷갈려하는 개념 중 하나입니다.

캡슐화가 코드나 데이터의 은닉에 포커스가 맞춰져있다면, 추상화는 클래스를 사용하는 사람이 필요하지 않은 메소드 등을 노출시키지 않고, 단순한 이름으로 정의하는 것에 포커스가 맞춰져 있습니다.
클래스 정의 시, 메소드와 속성만 정의한 것을 인터페이스라고 부릅니다. 이것이 추상화의 본질입니다.

##### 상속(Inheritance)

부모/자식으로 이야기하기도 하지만, 보다 그 특징을 자세하게 설명하는 용어는 "기본 클래스(base class)의 특징을 파생 클래스(derive class)가 상속받는다"로 표현하는 것이 적합합니다.

##### 다형성(Polymorphism)

Polymorphism이라는 단어의 poly는 "많은", 그리고 morph는 "형태"라는 뜻을 가지고 있습니다. 즉 "다양한 형태"를 가질 수 있다는 말이다.
"말하다"라는 동작의 본질은 "입으로 소리를 내다"를 의미합니다. 그러나, 각기 다른 동물들이 "말할 때" 제각각의 소리를 내는 것처럼, 객체 역시 똑같은 메소드라 하더라도, 다른 방식으로 구현될 수 있습니다.
TextBox는 가로로 긴 네모 상자와 커서가 있는 형태일 것이고, Select 박스는 눌렀을 때 선택지가 나오도록 화면에 그려야 할 것입니다. 이처럼 같은 이름을 가진 메소드라도 조금씩 다르게 작동합니다. 이것이 바로 다형성입니다.

##### oop의 주요개념의 장점

. 캡슐화는 코드가 복잡하지 않게 만들고, 재사용성을 높입니다.

. 추상화는 마찬가지로 코드가 복잡하지 않게 만들고, 단순화된 사용으로 인해 변화에 대한 영향을 최소화합니다

. 상속 역시 불필요한 코드를 줄여 재사용성을 높입니다.

. 다형성으로 인해 동일한 메소드에 대해 if/else if와 같은 조건문 대신 객체의 특성에 맞게 달리 작성하는 것이 가능해집니다.

#### extends

extends 키워드는 클래스를 다른 클래스의 자식으로 만들기 위해 class 선언 또는 class 식에 사용됩니다.

```js
class DateFormatter extends Date {
  getFormattedDate() {
    const months = [
      "Jan",
      "Feb",
      "Mar",
      "Apr",
      "May",
      "Jun",
      "Jul",
      "Aug",
      "Sep",
      "Oct",
      "Nov",
      "Dec",
    ];
    return `${this.getDate()}-${months[this.getMonth()]}-${this.getFullYear()}`;
  }
}

console.log(new DateFormatter("August 19, 1975 23:15:30").getFormattedDate());
// expected output: "19-Aug-1975"
```

#### super

super 키워드는 부모 오브젝트의 함수를 호출할 때 사용됩니다.
super()를 사용하지않는다면 부모 생성자를 호출할수없으므로 참조에러가 발생

#### this

this의 값은 함수를 호출하는 방법에 의해 결정된다.

#### 자바스크립트 객체지향적으로 쓰기

클래스 생성시 prototype이 생긴다.
인스턴트제작시 steeve.\__proto_

###### prototype
