# TO DEV TIL

## DOM
DOM은 Document Object Model의 약자로, HTML 요소를 Object(JavaScript Object)처럼 조작(Manipulation)할 수 있는 Model입니다. 즉, 여러분이 자바스크립트를 사용할 수 있으면, DOM으로 HTML을 조작할 수 있습니다.



오늘 익힌 간단한 문법
document.createElement('div')
document.append()
abc.textContent = 'div'
abc.classlist.add()
document.querySelector
document.quertSeltorall
abc.remove()
document.querySelector('#container').innerHTML = ''; 문제가 있어서 다른 메서드 를 사용

container의 첫번째자식 엘리먼트가 존재하면 , 첫번째 자식 엘리먼트를 삭제합니다.
```js
const container = document.querySelector('#container');
while (container.firstChild) {
  container.removeChild(container.firstChild);
}
```
container의 자식 엘리먼트가 1개만 남을 때까지, 마지막 자식 엘리먼트를 제거합니다.
```js
const container = document.querySelector('#container');
while (container.children.length > 1) {
  container.removeChild(container.lastChild);
}
```

```js
const tweets = document.querySelectorAll('.tweet')
tweets.forEach(function(tweet){
    tweet.remove();
})
// or
for (let tweet of tweets){
    tweet.remove()
}

```
Node.appendChild() 메소드는 한 노드를 특정 부모 노드의 자식 노드 리스트 중 마지막 자식으로 붙입니다. 만약 주어진 노드가 이미 문서에 존재하는 노드를 참조하고 있다면 appendChild() 메소드는 노드를 현재 위치에서 새로운 위치로 이동시킵니다

append vs appendchild
append는 여러개의 자식 엘리먼트를 동시에 추가가능
appendchild는 

### <script>태그를 head에 넣는것과 body가 끝나기전에 넣는것의 차이를 알고있나요?
렌더링 순서
parsing fetching executing parsing 
head부분에 넣었다면 렌더링을 멈춤

body에 넣었다면 html파일을 끝까지 읽고 자바스크립트를 다운로드 받음

### async?
async는 boolean 타입이기 때문에 선언하는것만으로도 true로 쓸 수 있다.
브라우저가 HTML을 파싱하다가 async을 확인하고 병렬로 다운로드를 명령만 해놓고 다시 파싱을 하고 JS 파일이 다운로드되면 그때 파싱을 멈추고
다운로드된 JS 파일을 실행하게된다. 이후 실행을 다하고나서 나머지 HTML을 파싱하게된다.

다운로드받는속도를 절약할 수 있지만 HTML이 파싱되기도전에 실행이 되기 때문에 querySelector로 DOM 요소를 조작하려 한다면
위험할 수 있으며 HTML을 파싱하는동안 언제든지 자바스크립트를 실행하기 위해서 멈출 수 있기때문에
사용자가 페이지를 보는데 여전히 시간이 조금 걸릴 수 있는 단점이 있다.
### defer?
HTML을 파싱을하다가 defer를 확인하고 JS 파일 다운로드를 명령시킨후 나머지 HTML을 끝까지 파싱하게 된다. 이후 마지막
파싱을 끝낸 다음에 다운로드되어진 JS 파일을 실행하도록한다.
### async / defer 의 차이
async 옵션으로 다수의 script 파일들을 다운로드 받게 되면
정의된script순서에 상관없이 다운로드 된 파일을 우선적으로 실행하기 때문에
JS파일이 순서에 의존적이라면 문제가 생길 수 있다.

반면,

defer 같은경우는 모든 script 파일들이 다운로드 된 이후에
실행 되기 때문에 훨씬 안전하다.
### 클릭이벤트를 붙이는 방법
div.Element.addEventListner('click',()=>{})
div.Element.onclick = () => {}
### innerHTML
string을parsing해 엘리먼트로 변환하여 집어넣는 속성
### textcontent
엘리먼트 내 content 부분에 text만 넣어주는 메소드

appendChild는 DOM 함수이고
append는 JavaScript 함수

append() 함수를 더 선호한다.
append를 할 때 문자열을 삽입할 수 있다.

먼저 이렇게 만들 수 있다.
document.getElementById('myId').append('Hello');

하지만 이렇게는 만들 수 없다.
document.getElementById('myId').appendChild('Hello');

아래와 같은 예외 발생
Uncaught TypeError: Failed to execute 'appendChild' on 'Node': parameter 1 is not of type 'Node'.


왜?
appendChild 함수에는 parameter(매개변수)와 같은 element(요소)가 필요하다.

이렇게 만들 수 없다.
document.getElementById('myId').appendChild('<p></p>');

그러나 이것은 만들 수 있다.
var p = document.createElement('p');
document.getElementById('myId').appendChild(p);
/^[0-9]*$/.test(value); mdn 에서 test 문법 검색 요망



