# TO DEV TIL

일급객체는

1. 변수에 할당가능
2. 다른 함수의 인자로 전달 가능
3. 다른함수의 결과로서 리턴가능
   문자열, 숫자 같은 다른 데이터처럼 사용가능

콜백함수는 함수에 인자로 전달되는 함수를 콜백 함수라고함!
함수를 리턴하는 함수는 커리함수
고차함수

1. 함수를 인자로 받는 함수
2. 함수를 리턴하는함수
3. 함수가 일급객체라서 고차함수로 활용가능

메소드는 객체에 들어있는 함수

### 고차함수

자바스크립트에는 특별한 대우를 받는 일급 객체 가있다(first-class citizen)
고차 함수(higher order function)는 함수를 인자(argument)로 받을 수 있고, 함수의 형태로 리턴할 수 있는 함수입니다.
다른 함수(caller)의 인자(argument)로 전달되는 함수를 콜백 함수(callback function)라고 합니다. 콜백 함수의 이름은, 어떤 작업이 완료되었을 때 호출하는 경우가 많아서, 답신 전화를 뜻하는 콜백이라는 이름이 붙여졌습니다.
콜백 함수초보 간단 정리
정의 함수에 파라미터로 들어가는 함수
용도 순차적으로쓰고싶을때 사용

함수를 리턴하는 함수'는 모양새가 특이한 만큼, 부르는 용어가 따로 있습니다. '함수를 리턴하는 함수'를 고안해 낸 논리학자 하스켈 커리(Haskell Curry)의 이름을 따, 커리 함수라고 합니다.

자기주도 학습
자바스크립트 배열 메소드 중 고차 함수 학습하기 (js array method)
forEach, find, filter, map, reduce, sort, some, every
filter 메소드에 들어가는 콜백 함수는 truthy 또는 falsy를 리턴할 수 있습니다. 그러나 filter 메소드에 들어가는 콜백 함수는 Deep equality를 통해 조건을 명확하게 밝히는 걸 권장합니다. 따라서 이 콘텐츠에서도 콜백 함수가 내부 조건에 따라 참(true) 또는 거짓(false)을 리턴하도록 구현하길 권장합니다.

### map

```js
let arr = [1, 2, 3];

let result = arr.map(function (ele) {
  return ele * 2;
});
result; //2,4,6
```

### filter

말그대로 원하는요소만 필터링 할수있음

```js
let arr = [1, 2, 3];
let result = arr.filter(function (ele) {
  return ele % 2 !== 0;
});
result;
//1,3
```

### reduce

배열의 각요소를 콜백 함수에 맞게 하나로 응축시킨 값을 리턴한다
arr.reduce((acc,cur)=>{
return acc+cur
})
배열을 하나의 값으로 만들어준다

```js
let arr = [1, 2, 3];
let result = arr.reduce(function (arr, cur, idx) {
  acc + cur;
  return acc;
});
result;
// 6
```

초기값을 정한다면

```js
let arr = [1, 2, 3];
let result = arr.reduce(function (arr, cur, idx) {
  acc + cur;
  return acc;
}, 1);
result;
// 7
```

arr.foreach((el) => console.log(el))
arr.find((el)=> el%2===1) 만족하는 맨처음 요소
let arr2 = [1,231,31,23,123] 원본배열을 건드림
arr2.sort()
arr.sort((a,b)=> a-b)
arr.some( (el)=> el %2 ===0) 콜백함수를 하나라도 만족한다면 트루를리턴
arr.every( (el)=> el %2 ===0) 콜백함수를 모도 만족한다면 트루를리턴

고차함수 27번
arr.reduce ((acc,cur) =>{
if(cur.length > acc.length) return cur
else return acc
},'')
고차함수 31번
let femalstudent = students.felter((student)= > {
if (student.gender === 'frmale'){
return true
}else {
return false
}

}
)
return femalsstudent.map((student)=>{
let totalgrade =student.gtades.redus((acc,cur)=>{
return acc+ cur
})
let average = totalgrade/student.grades.length
student.grades = average
return student
)
