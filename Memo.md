### MEMO
##### 헷갈렷던 코드 위주로 나열
```js 
function makePermutations(str) {
  // TODO: 여기에 코드를 작성합니다.
  let result = '';
  for(let i = 0; i < str.length; i++){
    for(let z = 0; z < str.length; z++){
      result = result + `${str[i]}${str[z]},`;
    }
  }return result.slice(0, result.length-1)
}
```
