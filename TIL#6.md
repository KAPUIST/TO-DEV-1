# TO DEV TIL

### 배열문제 
```js
function getAllLetters(str) {
  // TODO: 여기에 코드를 작성합니다.
  let result = Array.from(str)
  return result
}
```
Array.from() 메소드를 사용하면 str '1234'라고 가정했을때 
[1,2,3,4,] 배열상태로 하나씩 나온다.
spread operator라고 부르는 점세개...[] 이 방법도 가능하다 
```js
 const value = Math.max(...arr);
  return value
  ```
  for ...in // 객체 순환
for ...of // 배열 값 순환

##### for of 나in 문법이 이해가 쉽게 되지 않고있음.
```js
function getLargestElement(arr) {
  // javascript의 다양한 반복문 문법(syntax)을 검색해 봅니다. (`mdn for in` 또는 `mdn for of`)
  let max = arr[0];
  for (let el of arr) {
    if (el > max) {
      max = el;
    }
  }
  return max;
}
```

.join ??

#### 객체 object

```js
let user ={
firstname : 'taegwon',
lastname : 'son',
email: 'tkrk0@naver.com',
city : 'yangyang'};

user.cit
user.email
user['city']
```
이런식으로 . 을 활용한것을 dot notation 이라고 칭한다
[]을 활용한방법도있고 이것을 Bracket notation 이라고 칭함    key값이 동적인 변수일때 [] 사용함 
