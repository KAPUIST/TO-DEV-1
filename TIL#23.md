1. 재귀 함수의 입력값과 출력값 정의하기
   재귀 함수를 통해 풀고자 하는 문제, 즉 도달하고자 하는 목표를 정의하는 데 도움이 됩니다. 재귀적으로 사고하는 데에 가장 먼저 해야 할 일은 문제를 가장 추상적으로 또는, 가장 단순하게 정의하는 것입니다. 함수 arrSum의 경우 number 타입을 요소로 갖는 배열을 입력으로 받고, number 타입을 리턴합니다. 이를 좀 더 간단하게 표기하면 다음과 같습니다.

arrSum: [number] => number 2. 문제를 쪼개고 경우의 수를 나누기
주어진 문제를 어떻게 쪼갤 것인지 고민합니다. 문제를 쪼갤 기준을 정하고, 정한 기준에 따라 문제를 더 큰 경우와 작은 경우로 구분할 수 있는지 확인합니다. 일반적인 경우, 입력값으로 이 기준을 정합니다. 이때 중요한 관점은 입력값이나 문제의 순서와 크기입니다. 주어진 입력값 또는 문제 상황을 크기로 구분할 수 있거나, 순서를 명확하게 정할 수 있다면 문제를 구분하는 데 도움이 됩니다. 그리고 구분된 문제를 푸는 방식이 순서나 크기에 관계없이 모두 같다면, 문제를 제대로 구분한 것입니다.

함수 arrSum 의 경우 입력값인 리스트(배열)의 크기에 따라, 더 작은 문제로 나눌 수 있습니다. 그리고 arrSum([1, 2, 3, 4]) 를 구하는 방법과 arrSum([2, 3, 4]) 을 구하는 방법은 동일하므로, 이 구분은 적절하다고 판단할 수 있습니다.
이제 문제에서 주어진 입력값에 따라, 경우의 수를 나눕니다. 일반적으로 문제를 더 이상 쪼갤 수 없는 경우와 그렇지 않은 경우로 나눕니다.

함수 arrSum은 입력값이 빈 배열인 경우와 그렇지 않은 경우로 나눌 수 있습니다. 각각의 경우는 다른 방식으로 처리해야 합니다.
arrSum: [number] => number
arrSum([ ])
arrSum([e1, e2, ... , en]) 3. 단순한 문제 해결하기
문제를 여러 경우로 구분한 다음에는, 가장 해결하기 쉬운 문제부터 해결합니다. 이를 재귀의 기초(base case)이라고 부릅니다. 재귀의 기초는 나중에 재귀 함수를 구현할 때, 재귀의 탈출 조건(재귀 호출이 멈추는 조건)을 구성합니다.

함수 arrSum 을 더 이상 쪼갤 수 없는 경우는 입력값이 빈 배열일 경우이고, 이때 arrSum([]) 의 리턴값은 0입니다.
arrSum: [number] => number
arrSum([ ]) = 0
arrSum([e1, e2, ... , en]) 4. 복잡한 문제 해결하기
남아있는 복잡한 경우를 해결합니다.

길이가 1 이상인 배열이 함수 arrSum 에 입력된 경우, 맨 앞의 요소에 대한 결과를 따로 구하고(배열의 맨 앞의 요소이기 때문에 head라고 이름 붙이겠습니다.), 나머지 요소를 새로운 입력값으로 갖는 문제로 구분하고, 이를 해결하여 얻은 결과를 head에 더합니다.
arrSum: [number] => number
arrSum([ ]) = 0
arrSum([e1, e2, ... , en]) = e1 + arrSum([e2, ..., en])
배열을 head와 나머지 부분(tail)으로 구분하는 방법만 안다면, 함수 arrSum을 재귀적으로 구현할 수 있습니다.
