### JSON vs. BSON

이번 콘텐츠에서는 도큐먼트(Document)를 올바르게 작성하는 방법과 도큐먼트(Document)가 표현되는 방법을 학습합니다.
shell을 이용하여 도큐먼트를 조회하거나 업데이트할 때, 도큐먼트는 JSON(JavaScript Object Notation) 형식으로 출력됩니다.
JSON 형식으로 도큐먼트를 작성하기 위해서는, 다음과 같은 조건을 만족해야 합니다.

BSON은 다음 세 가지 특성을 갖도록 설계되었습니다.

1. 경량
   공간 오버헤드를 최소화하는 것은 모든 데이터 표현 형식에서 특히 네트워크를 통해 사용될 때 중요합니다.

2. 순회 가능
   BSON은 쉽게 통과하도록 설계되었습니다. 이것은 MongoDB 의 기본 데이터 표현으로서의 역할에서 중요한 속성입니다 .

3. 효율적인
   BSON으로 데이터 인코딩 및 BSON에서 디코딩은 C 데이터 유형을 사용하기 때문에 대부분의 언어에서 매우 빠르게 수행할 수 있습니다.

BSON은 컴퓨터의 언어에 가까운 이진법에 기반을 둔 표현법입니다. 따라서 JSON 보다 메모리 사용이 효율적이며 빠르고, 가볍고, 유연합니다.
뿐만 아니라, BSON의 사용으로 더 많은 데이터 타입을 사용할 수 있습니다.

MongoDB는 JSON 형식으로 작성된 것은 무엇이든 데이터베이스에 추가할 수 있고, 쉽게 조회할 수 있습니다.
그러나 그 내부에서는 속도, 효율성, 유연성의 장점이 있는 BSON으로 데이터를 저장, 사용하고 있습니다.

### jSON & BSON

데이터를 가져오거나(import), 내보내는(export) 경우에따라 효율적인 데이터 형식이 존재합니다.

MongoDB의 데이터는 BSON의 형태로 저장이되고, 보통 읽기쉬운 JSON 의형태로 출력됩니다.
두형식의 특징이 다르기떄문입니다,

만약 단순히 백업 저장을 하기위해서 라면 가볍고 빠른 BSON 의 형태를 사용하는 편이 좋습니다. 그러나 데이터를 내보낸후 조회를 하거나 출력을해야한다면사람이읽기쉬운 JSON의 형식이 바람직합니다.그래서 조건에 따라, 가져오거나 내보낼 때 사용 가능한 명령어가 각각 존재합니다.

#### 크게 두가지로 나뉩니다.

먼저 JSON 형식으로 데이터를 가져오고 내보내기 위한 명령어인 mongoimport와 mongoexport가 있고,
BSON 형식으로 가져오고 내보내기 위한 명령어인 mongorestore와 mongodump가 있습니다.

| JSON         | BSON         |
| ------------ | ------------ |
| mongoimport  | mongorestore |
| mongtoexport | mongodump    |

##### Export

```js
mongodump --uri "<Atlas Cluster URI>"

Export data in BSON
```

```js
mongoexport --uri "<Atlas Cluster URI>"
            --collection=<collection name>
            --out=<filename>.json

Export data in JSON
```

일단 이를 사용하기위해서는 Atlas Cluster URI가 필요합니다 해당 URI는 일반 웹의 URI와 형식이 같고, username, password, cluster 주소로 이루어져 있습니다.

mongodump를 하는 경우에는 별다른 쿼리가 없지만,
mongoexport를 하는 경우에는 해당 데이터베이스의 컬렉션 이름, 파일 이름까지 정확하게 작성해줘야 합니다.

##### Import

```js
mongorestore --uri"<Atlas Cluster URI>"
             --drop dubmp
import data in BSON dump
```

```js
mongoimport --uri"<Atlas Cluster URI>"
            --drop=<filename>.json
import data in JSON
```
