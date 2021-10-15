# TO DEV TIL

### HTML
### STRUCTURE (구조)

Hyper Text Markup Language 의 약자 HTML
웹페이지의 틀을 만드는 마크업 언어.
html 은  tag(<> 부등호)로 묶인 html 의 기본 요소.
html 이라는 확장자를 사용

### tree structure
```html
<!DOCTYPE html>           이 문서가 HTML문서임을 명시
<html>       html 시작 태그로, 문서 전체의 틀을 구성 
 <head>          head 태그는 문서의 메타데이터를 선언
  <title>page title<!title>  문서의 제목, 브라우저의 탭에 보여짐
 </head>           </태그이름>은 해당 태그가 끝났음을 의미
 <body>           body 태그는 문서의 내용을 담는 곳
  <h1>hello world</h1>            heading을 의미하며, 크기에 따라 h1~h6까지있음
  <div> condtents here         content division을 의미하며, 줄바꿈됨 
    <span> here too!</span> 줄바꿈이 없는 content컨테이너
    </div>  div 태그가 끝났음을 의미 
  </body>  body태그가 끝났을을 의미
</html>   html 태그가 끝났음을 의미
```
### self - closing tag
태그 내부에 내용이 없다면 (<tag> </tag>와 같이 표현되는경우) <tag/>와 같이 표현가능
```html
<img src="ddd.png"></img>
src 의 값에 ddd라는 사진  정보가 있음.

<img src="ddd.png" />
```
### html 에서 가장 많이 사용되는 태그
<div> division
<span> span
<img> image 
뒤에 속성 src를 붙혀야함
<a> link 뒤에 hreaf(속성)연결할 주소를 지정 라는 것을 붙힘 targen="_blank" 새창으로갈수있음
<ul>&<li> unordered list & list item  ol 로 바뀌게 되면 너버링이 추가됨
<input> input(text, radio, checkbox)
input type="text""
<textarea> multi-line text input
<button> button
<p> HTML <p> 엘리먼트는 paragraph(문단)의 약자로, 하나의 문단을 표현하기 위하여 사용됩니다. HTML 문서 작성 시, 가능하면 이 엘리먼트의 본래 목적에 맞게 사용하는 것이 권장됩니다.
<section> HTML <section> 엘리먼트는 웹 페이지의 큰 의미 단위가 될 수 있는 어떤 것이든 묶어서 하나의 구역을 구분하는데 사용됩니다. 이 엘리먼트는 HTML5 표준의 탄생과 함께 생겨난 시맨틱 엘리먼트의 일부입니다. 엘리먼트의 이름에 의미를 충분히 담고 있기 때문입니다.

<div> 엘리먼트는 HTML5 이전에는 하나의 구역(division)을 나타내기 위해 사용할 수 있었지만, 지금은 어떤 큰 구역을 구분하기 위하여 사용되는 것은 지양되고 있습니다. 다만, 작은 구역에서 불가피하게 div를 사용해야 하는 "최악(as a last resort)"로는 사용해도 괜찮습니다. 좋은 스택 오버플로우 답변을 소개합니다.
div vs span 
div는 한줄을 사용하지만 span 태그는 한줄을 사용하지않음
### 오늘 배운 간단한 HTML 만들어보기
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <h1> 제목은 김도남 </h1>
  <div> 도남이는 자신보다 4살 어린 여자친구를 만나고있음
    <span> 이름은 김은선</span>
    <span1>양여고나옴</span1>
  </div>
  <div>김도남  롤 티어 </div>
  <a href="https://www.op.gg/summoner/userName=%EB%BD%95%EB%B6%84" target="_blank">바로가기</a> 
  <ol>
    <li> 김도남 170 안댐</li>
    <li> 김도남 골드임</li>
    <li> 도남이는 사랑꾼 과연?
      <ol>
        <li>귀여운 도남이</li> 
      </ol>
    </li>
  </ol>

  <input type="text">
  <div>
    <input type="radio" name="도남이의 비밀친구" value="맞다"> 맞다
    <input type="radio" name="도남이의 비밀친구" value="아니다"> 아니다
  </div>
  <textarea></textarea>
  <div>
    ID<input type="text" placeholder="type here.">
  </div>
  <div>
    password<input type="password">
    <input type="checkbox" > 동의
    <input type="checkbox" > 미동의
  </div>
</head>
```
