### 데이터베이스의 필요성

1. In-Memory
   먼저 JavaScript에서 데이터를 다룰 때에는 프로그램이 실행될 때에만 존재하는 데이터가 있습니다.

JavaScript에서 변수를 만들어 저장한 경우, 프로그램이 종료될 때 해당 프로그램이 사용하던 데이터도 사라집니다. 이 말은 변수 등에 저장한 데이터가 프로그램의 실행에 의존한다는 말입니다. 예기치 못한 상황으로부터 데이터를 보호할 수 없고, 프로그램이 종료된 상태라면 데이터를 원하는 시간에 받아올 수 없으며, 데이터의 수명이 프로그램의 수명에 의존하게 됩니다.

2. File I/O
   파일을 읽는 방식으로 작동하는 형태를 말합니다. 엑셀 시트나 CSV 같은 파일의 형태는 In-Memory에 비해 데이터를 저장하는 방식으로 적절해 보입니다. 그러나 한계가 분명히 존재합니다.

- 데이터가 필요할 때마다 전체 파일을 매번 읽어야 합니다. 파일의 크기가 커질수록 이 작업은 버겁고, 비효율적이어서 File I/O 방식의 큰 단점입니다.
- 파일이 손상되거나 여러 개의 파일들을 동시에 다뤄야 하거나 하는 등 복잡하고 데이터량이 많아질수록 데이터를 불러들이는 작업이 점점 힘들어집니다.
  반면에 관계형 데이터베이스에서는 하나의 CSV 파일이나 엑셀 시트를 한 개의 테이블로 저장할 수 있습니다. 한 번에 여러 개의 테이블을 가질 수 있기 때문에 SQL 을 활용해 데이터를 불러오기 수월합니다. 또한, 엑셀 시트와 CSV 파일 등처럼 특정 형태의 파일은 대용량의 데이터를 저장하기 위한 목적이 아닙니다.

### SQL

하나의 언어인 Structured Query Language (SQL)은 데이터베이스 언어로, 주로 관계형 데이터베이스에서 사용합니다. 예를 들어 MySQL, Oracle, SQLite, PostgreSQL 등 다양한 데이터베이스에서 SQL 구문을 사용할 수 있습니다.

SQL이란 데이터베이스 용 프로그래밍 언어입니다. 데이터베이스에 쿼리를 보내 원하는 데이터를 가져오거나 삽입할 수 있습니다. 그리고 이름에서 유추할 수 있듯이, SQL은 (relation 이라고도 불리는) 데이터가 구조화된(structured) 테이블을 사용하는 데이터베이스에서 활용할 수 있습니다.

SQL을 사용할 수 있는 데이터베이스와 달리, 데이터의 구조가 고정되어 있지 않은 데이터베이스를 NoSQL이라고 합니다. 관계형 데이터베이스와는 달리, 테이블을 사용하지 않고 데이터를 다른 형태로 저장합니다. NoSQL의 대표적인 예시는 MongoDB 와 같은 문서 지향 데이터베이스입니다.

### SQL 기본 쿼리문

- Select
- Where
- And, Or, Not
- Order By
- Insert Into
- Null Values
- Update
- Delete
- Count
- Like
- Wildcards
- Aliases

- Joins
  - Inner Join
  - Left Join
  - Right Join

Group By

##### 데이터베이스 관련 용어

- SQL Create DB
- SQL Drop DB
- SQL Create Table
- SQL Drop Table
- SQL Alter Table
- SQL Not Null
- SQL Unique
- SQL Primary Key
- SQL Foreign Key
- SQL Default
- SQL Auto Increment
- SQL Dates

### 데이터베이스 관련 명렁어

생성

```js
CREATE DATABASE 데이터베이스_이름
```

사용

```js
USE 데이터베이스 이름`
```

### ACID

데이터 베이스 트랜젝션이 발생할때 그 안정성을 보장할수있는 성질

Transaction
데이터베이스의 상태를 변환시키는 논리적 기능을 수행하기위해 행해지는 하나이상의 쿼리를 모아놓은 하나의 작업 단위

#### Atomicity

하나의 트랜젝션 내에서는 모든연산이 성공하거나 모두 실패해야한다

#### Consistency

하나의 트랜젝션 전후에 데이터베이스의 일관된 상태가 유지되어야 한다.

#### Isolation

각각의 트랜젝션은 독립적. 서로의 연산을 확인받거나 영향을 줄수없다.

#### Durability

하나의 성공된 트랜젝션에 대한 로그가 기록되고 영구적으로 남는다.
