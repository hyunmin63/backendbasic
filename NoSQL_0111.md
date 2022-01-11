What is NoSQL
================
## 1. NoSQL DB. 비관계성 데이터베이스
NoSQL DB란, 행과 테이블을 사용하는 SQL(관계형) DB보다 훨씬 다양한 방식으로 빠르게 바뀌는 대량의 비정형 데이터를 처리할 수 있음.

대부분의 전형적인 DB System에서는 행과 열로 이루어진 Table 형식의 Schema를 사용하는데, NoSQL DB는 이 Table Schema를 사용하지 않음.
대신 저장되는 데이터 형식마다, 특정 요구사항에 맞게 각각 최적화된 Storage Model을 사용한다.

NoSQL DB가 저장할 수 있는 데이터는 Key-Balue Pair, JSON Documents, 모서리-꼭짓점 그래프 등등이 있음.

요러한 모든 DB Storage가 갖는 공통점은, 관계형 모델을 사용하지 않는다는 것!
관계형 데이터베이스보다는, 데이터의 저장 및 검색을 위한 매커니즘을 제공함.

또한 스키마와 관계가 없는 만큼 지원하는 데이터 형식과 데이터를 Query할 수 있는 방법도 좀 더 다양하고 구체적일 수 있다.
예를 들어, 시계열 데이터 저장소는 시간 기반 데이터 시퀀스에 대한 Query에 최적화되어있고, Graph Data Storage는 Entity간의 가중치가 적용된 관계를 탐색하는데 최적화되어있음.
(여기서 Entity란 자바에서 Class같은 느낌. 다양한 Instances가 존재하고 공통되는 Attribute가 있다고 함)

이와 같이 특정 데이터 모델 및 액세스 패턴에 대해 최적화되어있기 때문에, 이런 환경에서 반복 작업 수행 시 매우 높은 성능을 가짐.

## 2. 문서 데이터 저장소 (MongoDB, CouchDB)
Entity에서 명명된 문자열필드 및 Object Data Value Set(객체 데이터 값 집합)을 관리함.
일반적으로 JSON 문서 형식으로 데이터 저장.
이 데이터 구조는 한 개 이상의 key-value pair로 이루어져 있다.

```
  {
    "id": Opjectid("5099803df3f4948bd2f98391",
    "username": "velopert",
    "name": {first:"M.J.", last:"Kim"}
  }
```

여기서 id, username, name이 Key이고, 각 Key에 대응되는 오른쪽의 값이 Value이다.
Document는 정해지지 않은 동적 Schema를 갖고 있기 때문에, 같은 Collection 내의 Document끼리 서로 다른 Schema를 가질 수 있음.
쉽게 말하면 서로 다른 데이터(서로 다른 종류의 Key)를 가질 수 있음!

MongoDB는 C++ 기반의 DB로서 유연하고 반복된 개발을 위해 강력하고 직관적인 API를 제공하는 널리 쓰이는 문서 데이터베이스.

## 3. 키-값 데이터 저장소 (DynamoDB)
앞서 살펴본 Document를 Key값을 통해서 검색할 수 있는 구조.
이 때 Key는 데이터를 균등하게 분산하는 데 도움이 되는 문서에 대한 고유 식별자!
Key는 문서 생성 시에 자동으로 만들 수도 있고, 문서의 특징을 하나 지정해서 이 값을 통해 만들 수도 있음.

![image](https://user-images.githubusercontent.com/97514510/148930024-8b4e4bfc-7e7d-49e4-a4b7-6b122f555be2.png)

