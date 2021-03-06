#NoSql
- No sql 은 not only sql 의 약어이다.
- 반정규화에 의존하며 저장소에 테라바이트나 페타바이트 단위의 거대한 데이터를 처리할 때 애플리케이션이 가능한 빨리 데이터를 찾을 수 있도록 전체 문서나 그래프를 키-값 쌍으로 저장한다.
- 기본적으로 데이터 베이스는 계층형 -> 네트워크형 -> 관계형 으로 발전해 왔으며, 최근 대용량 데이터 처리가 이슈되면서
아래와 같은 관계형 데이터 베이스의 장단점의 보완 및 활용하고자 no-sql 에 대한 관심이 높아지고 있다.

###관계형 데이터 베이스의 장점
- 데이터의 일관성을 보증할 수 있다. (트랜잭션)
- 정규화를 전제로 하고 있기 때문에 갱신 시의 비용이 적게 든다.
- 조인이나 복잡한 검색조건으로 검색이 가능하다
- 참고 자료나 노하우가 많이 있다. (검증되고 성숙된 기술)

###관계형 데이터 베이스의 단점
- 대량의 데이터 입력 처리 시 성능 이슈
- 갱신이 발생한 테이블의 인덱스 생성이나 스키마 변경에 대한 처리 이슈
- 컬럼을 확실히 정의하기 어려운 경우에 대한 처리 이슈
- 단순히 빨리 결과를 조회하고자 할때의 성능 이슈

- 일반적으로 데이터 베이스 저장소의 처리 성능을 확장하기 위한 노력은 2가지로 분류될수 있다. 스케일업과 스케일 다운이다.
 
###스케일 업 방식
- 사용중인 서버 자체를 고성능으로 바꿔서 처리능력을 향상시키는 방법
- 상당히 많은 비용이 발생하지만, 소스에 대한 변경이 없다
 
###스케일 다운 방식
- 저가의 여러 장비를 사용하여 처리 능력을 향상 시킴
- 저가의 비용으로도 원하는 성능을 확보할 수 있지만, 소스 수정이 필요하다. ->NO-SQL 에서 제공하는 방식

###NO-SQL 데이터 베이스
- 조인 연산이 불가능하며, 각 데이터가 독립적으로 설계 되어 있어 데이터를 여러 서버에 분산하여 작업 하는 방식
- 데이터를 여러 서버에 분산하는 것을 통하여 각 서버에서 처리하는 데이터의 양이 줄고 따라서 대량의 데이터의 입출력이 있어도 처리가 쉬워진다.
- 일반적으로 관계형 데이터 베이스의 경우에는 고가의 장비를 마스터-슬래이브 혹은 액티브-스탠바이 형태로 구성하여 서비스하고 있는 경우가 많음
- NO-SQL 에서 이야기 하는 구성은 이런 구성이 아닌 10대 혹은 100대 정도의 저가의 서버들을 클러스터링 혹은 샤팅 등의 방법으로 데이터를 쪼개서 나누어 처리하는 방식을 말한다.
- NoSQL은 빠른 Insert 성능을 내기위해 많은 DB의 좋은 기능을 포기하였다. 예를들어 "트랜젝션"이 대표적

###CAP
- C(일관성) : 모든 사용자들에게 같은 시간에 같은 데이터를 보여 주어야 한다
- A(유효성) : 모든 클라이언트 들이 읽기 및 쓰기가 가능해야 한다. 즉, 하나의 노드가 장애가 일어 나더라도 다른 노드에는 영향을 미치면 안된다.
- P(분산가능) : 물리적 네트워크 분상 환경에서 시스템 동작이 원할하게 이루어 져야 한다. 즉, 네트워크 전송 중 데이터 손실 상황이 와도 시스템은 정상적으로 동작을 해야한다

###NoSQL 데이터베이스
- MongoDB : 데이터를 JSON 객체로 저장하고 같은 필드 전부를 다른 유사 객체와 공유하지 않는다.
- 카산드라 : 데이터를 컬럼 패밀리로 저장한다. 테이블도 비슷하지만 행은 같은 열들을 공유할 필요가 없다.
- Memcached : 분산 키-값 저장소 캐시
- 레디스 : 클러스터된 영구 키-값 저장소
