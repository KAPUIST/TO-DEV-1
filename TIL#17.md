### 클라이언트 서버 아키텍처, 다른 말로는 2티어 아키텍처라고 불리는 설계 방식에 대해 알아봅니다.

클라이언트 : 웹사이트 (웹앱), 스마트폰/태블릿 앱/ 데스크탑 앱

서버 : 웹서버, 파일서버, 메일서버, 데이터베이스 서버

클라이언트는 보통 플랫폼에 따라 구분됩니다. 브라우저를 통해 주로 이용하는 웹(Web) 플랫폼에서의 클라이언트는 웹사이트 또는 웹 앱이라고 부릅니다.

iOS나 안드로이드와 같은 스마트폰/태블릿 플랫폼, 그리고 윈도우와 같은 데스크탑 플랫폼에서 이용하는 앱 역시 클라이언트가 될 수 있습니다.

서버는 무엇을 하느냐에 따라 종류가 달라집니다. 파일 서버는 파일을 제공하는 앱, 웹 서버는 웹사이트에서 필요로 하는 정보들을 제공하는 앱(이후 주로 우리가 만들게 될 서버입니다), 메일 서버는 메일을 주고 받을 수 있도록 도와주는 앱입니다.

데이터베이스도 데이터 제공자로서 일하므로 일종의 서버라고 볼 수 있습니다.

### 클라이언트와 서버의 통신

클라이언트와 서버간의 통신은 요청과 응답으로 구성되어있고 요청이 있어야만 응답이 옵니다.

#### 프로토콜

프로토콜은 통신 규약, 즉 약속입니다. 손님이 주문을 받는 사람에게 대뜸 찾아가, 외계어로 주문을 할 수 없듯, 주문을 하기 위해서는 꼭 지켜야 하는 약속이 몇가지 존재합니다.

웹애플리케이션 프로토콜 : HTTP를 사용합니다

프로토콜은 커피주문과 비슷하다 주문할수있는 여러방법이 있는것이다

1. 직접카운터로 찾아가기
2. 모바일 주문
3. 키오스크

#### 주요프로토콜

OSI 7 Layers
응용계층 :

1. HTTP : 웹에서 HTML jSON 등의 정보를 주고받는 프로토콜
2. HTTPS : HTTP 에서 보안이 강화된 프로토콜
3. FTP : 파일전송 프로토콜
4. SMTP : 메일을 전송하기위한 프로토콜
5. SSH : CLI 환경의 원격 컴퓨터에 접속하기 위한 프로토콜
6. RDP : Windows 계열의 원격 컴퓨터에 접속하기위한 프로토콜
7. WebSocket : 실시간 통신, Push등을 지우너하는 프로토콜

전송계층

1. TCP : HTTP, FTP 통신의 등의 근간이되는 인터넷 프로토콜
2. UDP : (양방향의 TCP와는 다르게)단방향으로 작동하는 훨씬더 단순하고 빠르지만, 신뢰성이 낮은 인터넷 프로토콜

### API

api는 마치 식당에서 메뉴판을 제공하듯 서버의 리소스를 잘활용할수있도록 API를제공해야 합니다
API는 Application Programming Interface의 약자이며, Interface의 사전적 의미는 "의사소통이 가능"하도록 만들어진 "접점"을 의미합니다. 이 의미에 따르면, 메뉴판도 인터페이스라고 볼 수 있습니다.

### HTTP Messages

HTTP는 HyperText Transfer Protocol의 줄임말로, HTML과 같은 문서를 전송하기 위한 Application Layer 프로토콜입니다. HTTP는 웹 브라우저와 웹 서버의 소통을 위해 디자인되었습니다. 전통적인 클라이언트-서버 모델에서 클라이언트가 HTTP messages 양식에 맞춰 요청을 보내면, 서버도 HTTP messages 양식에 맞춰 응답합니다. HTTP는 특정 상태를 유지하지 않는 특징이 있습니다.

. HTTP의 특징: Stateless(무상태성)

HTTP messages 는 클라이언트와 서버 사이에서 데이터가 교환되는 방식입니다. HTTP messages에는 다음과 같은 두 가지 유형이 있습니다.

요청(Requests)
응답(Responses)
HTTP messages는 몇 줄의 텍스트 정보로 구성됩니다. 그러나 개발자는 이런 메시지를 직접 작성할 필요가 거의 없습니다. 구성 파일, API, 기타 인터페이스에서 HTTP messages를 자동으로 완성합니다.

요청(Requests)과 응답(Responses)은 다음과 같은 유사한 구조를 가집니다.

start line : start line에는 요청이나 응답의 상태를 나타냅니다. 항상 첫 번째 줄에 위치합니다. 응답에서는 status line이라고 부릅니다.
HTTP headers : 요청을 지정하거나, 메시지에 포함된 본문을 설명하는 헤더의 집합입니다.
empty line : 헤더와 본문을 구분하는 빈 줄이 있습니다.
body : 요청과 관련된 데이터나 응답과 관련된 데이터 또는 문서를 포함합니다. 요청과 응답의 유형에 따라 선택적으로 사용합니다.
이 중 start line과 HTTP headers를 묶어 요청이나 응답의 헤드(head)라고 하고, payload는 body라고 이야기합니다.

#### Request

##### Start line

HTTP 요청은 클라이언트가 서버에 보내는 메시지입니다. Start line에는 세 가지 요소가 있습니다.

1. 수행할 작업(GET, PUT, POST 등)이나 방식(HEAD or OPTIONS)을 설명하는 HTTP method를 나타냅니다. 예를 들어 GET method는 리소스를 받아야 하고, POST method는 데이터를 서버로 전송합니다.
2. 수행할 작업(GET, PUT, POST 등)이나 방식(HEAD or OPTIONS)을 설명하는 HTTP method를 나타냅니다. 예를 들어 GET method는 리소스를 받아야 하고, POST method는 데이터를 서버로 전송합니다.
   . rigin 형식 : ?와 쿼리 문자열이 붙는 절대 경로입니다. POST, GET, HEAD, OPTIONS 등의 method와 함께 사용합니다.
   POST / HTTP 1.1
   GET /background.png HTTP/1.0
   HEAD /test.html?query=alibaba HTTP/1.1
   OPTIONS /anypage.html HTTP/1.0
   . absolute 형식 : 완전한 URL 형식으로, 프록시에 연결하는 경우 대부분 GET method와 함께 사용합니다.
   GET http://developer.mozilla.org/en-US/docs/Web/HTTP/Messages HTTP/1.1
   . authority 형식 : 도메인 이름과 포트 번호로 이루어진 URL의 authority component 입니다. HTTP 터널을 구축하는 경우, CONNECT와 함께 사용할 수 있습니다.
   CONNECT developer.mozilla.org:80 HTTP/1.1
   . asterisk 형식 : OPTIONS 와 함께 별표(_) 하나로 서버 전체를 표현합니다.
   OPTIONS _ HTTP/1.1
3. HTTP 버전에 따라 HTTP message의 구조가 달라집니다. 따라서 start line에 HTTP 버전을 함께 입력합니다.

### REST API
