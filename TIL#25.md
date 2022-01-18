### Big-O 표기법

시간 복잡도를 표기하는 방법은 다음과 같습니다.

- Big-O(빅-오)
- Big-Ω(빅-오메가)
- Big-θ(빅-세타)

O(1)는 constant complexity라고 하며, 입력값이 증가하더라도 시간이 늘어나지 않습니다. 다시 말해 입력값의 크기와 관계없이, 즉시 출력값을 얻어낼 수 있다는 의미입니다.

```js
function O_1_algorithm(arr, index) {
  return arr[index];
}

let arr = [1, 2, 3, 4, 5];
let index = 1;
let result = O_1_algorithm(arr, index);
console.log(result); // 2
```

O(n)은 linear complexity라고 부르며, 입력값이 증가함에 따라 시간 또한 같은 비율로 증가하는 것을 의미합니다.

```js
function O_n_algorithm(n) {
  for (let i = 0; i < n; i++) {
    // do something for 1 second
  }
}

function another_O_n_algorithm(n) {
  for (let i = 0; i < 2n; i++) {
    // do something for 1 second
  }
}
```

O(log n)은 logarithmic complexity라고 부르며 Big-O표기법중 O(1) 다음으로 빠른 시간 복잡도를 가집니다.
자료구조에서 배웠던 BST(Binary Search Tree)를 기억하시나요?
BST에선 원하는 값을 탐색할 때, 노드를 이동할 때마다 경우의 수가 절반으로 줄어듭니다. 이해하기 쉬운 게임으로 비유해 보자면 up & down을 예로 들 수 있습니다.

1~100 중 하나의 숫자를 플레이어1이 고른다 (30을 골랐다고 가정합니다).
50(가운데) 숫자를 제시하면 50보다 작으므로 down을 외친다.
1~50중의 하나의 숫자이므로 또다시 경우의 수를 절반으로 줄이기 위해 25를 제시한다.
25보다 크므로 up을 외친다.
경우의 수를 계속 절반으로 줄여나가며 정답을 찾는다.

O(n2)은 quadratic complexity라고 부르며, 입력값이 증가함에 따라 시간이 n의 제곱수의 비율로 증가하는 것을 의미합니다.

```js
function O_quadratic_algorithm(n) {
  for (let i = 0; i < n; i++) {
    for (let j = 0; j < n; j++) {
      // do something for 1 second
    }
  }
}

function another_O_quadratic_algorithm(n) {
  for (let i = 0; i < n; i++) {
    for (let j = 0; j < n; j++) {
      for (let k = 0; k < n; k++) {
        // do something for 1 second
      }
    }
  }
}
```

O(2n)은 exponential complexity라고 부르며 Big-O 표기법 중 가장 느린 시간 복잡도를 가집니다.

```js
function fibonacci(n) {
  if (n <= 1) {
    return 1;
  }
  return fibonacci(n - 1) + fibonacci(n - 2);
}
```
