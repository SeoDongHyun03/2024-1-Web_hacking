# 비관계형 데이터베이스  
RDBMS는 **스키마를 정의**하고 데이터를 **2차원 테이블** 형태로 저장합니다. 이는 **복잡**할 뿐만 아니라, **저장해야 하는 데이터가 많아지면 용량의 한계**에 다다를 수 있다는 단점이 있다.  
비 관계형 데이터베이스(Non-Relational DBMS (NRDBMS, NoSQL)) 
## 비관계형 데이터베이스  
NoSQL은 **SQL를 사용하지 않고 복잡하지 않은 데이터를 저장**해 **단순 검색 및 추가 검색 작업**을 위해 매우 **최적화된 저장 공간**인 것과, **키-값**을 사용해 데이터를 저장하는 특징이 있다.  
다만 NoSQL 은 **다양한 DBMS가 존재**하기 때문에 **각각의 구조와 사용 문법을 익혀야한다**는 단점이 있다.  
# MongoDB  
## MongoDB  
MongoDB는 **JSON 형태인 도큐먼트(Document)** 를 저장한다.  
1. 스키마를 따로 정의하지 않아 각 컬렉션(Collection)에 대한 정의가 필요하지 않습니다.  
2. JSON 형식으로 쿼리를 작성할 수 있습니다.   
3. _id 필드가 Primary Key 역할을 합니다.  
```MongoDB
$ mongosh
> db.user.insertOne({uid: 'admin', upw: 'secretpassword'})
{ acknowledged: true, insertedId: ObjectId("5e71d395b050a2511caa827d")}
> db.user.find({uid: 'admin'})
[{ "_id" : ObjectId("5e71d395b050a2511caa827d"), "uid" : "admin", "upw" : "secretpassword" }]
```
다음은 MongoDB 에서 데이터를 삽입하고 조회하는 쿼리의 예시입니다.  
각 **DBMS에서 status의 값이 "A"** 이고, **qty의 값이 30보다 작은 데이터를 조회**하는 쿼리는 다음과 같습니다. 
```SQL
SELECT * FROM inventory WHERE status = "A" and qty < 30;
```
MongoDB의 경우 $ 문자를 통해 연산자를 사용할 수 있습니다.  
다음은 위의 쿼리문을 MongoDB로 적은 예시입니다.  
```MongoDB
db.inventory.find(
  { $and: [
    { status: "A" },
    { qty: { $lt: 30 } }
  ]}
)
```
## MongoDB 연산자  
## MongoDB 기본 문법  
# Redis  
## Redis  
# CouchDB  
## CouchDB  
# 퀴즈  
