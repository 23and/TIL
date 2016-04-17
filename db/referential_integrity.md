#Referential integrity(참조 무결성)
- 테이블간의 관계가 항상 consistent하게 유지되어야 한다는 개념.
- 테이블이 Primary key와 Foreign key로 연결되는 관계를 가질 때, 어떤 foreign key던지 항상 연결되어 있는 다른 테이블의 primary key(즉, 레퍼런스)가 제대로 존재해야 한다. 
- 업데이트나 삭제가 일어나도 연결된 두테이블이 항상 synchronized 되게 해주는 법칙.
- 관계형 데이터베이스에서 서로 관련된 테이블의 레코드간의 관계를 유효하게 하고, 사용자가 실수로 관련데이터를 삭제,변경 하지 않도록 하기 위해서 사용.
- A->B : A가 B를 참조하고 있을때 B를 삭제할 때 발생.이를 처리하기 위해서는 A를 먼저 삭제후 B를 처리
- 한 릴레이션이 다른 릴레이션의 기본 키와 같은 도메인 상에 정의된 속성을 가질 때 이 속성의 값은 널(null)이거나 이 속성을 기본 키로 갖는 릴레이션 안에 존재하는 값이어야 한다는 조건.
 - 외래키의 값이 반드시 다른 릴레이션의 기본키이어야 한다.
 - 외래키는 null값을 가질 수 없다.
 
###Referential integrity 가 위반되는 경우
````
- Referenced table에 없는 데이터를 참조한답시고 referencing table의 foreign key 칼럼에 넣을 때
- 참조 당하는 Referenced table의 primary key가 삭제될 때
- 참조 당하는 Referenced table의 primary key가 다른 값으로 업데이트 될 때
````
- 위반될 경우에 어떤 일이 일어날 지 미리 정해 놓을 수도 있다. 
 - 아무런 액션도 취하지 않는다, null값을 넣는다
 - CASCADE인데 참조 당하는 테이블의 primary key를 지우거나 업데이트 할 경우 해당 테이블을 참조한 테이블의 foreign key도 줄줄이 같이 삭제(CASCADING DELETE)하거나 같이 업데이트(CASCADING UPDATE)하는 것

- 참조 : crack-tech-interview.com