#MySQL InnoDB Auto Increment

- InnoDB는 Auto Increment 값 생성을 위해 테이블 별로 Auto-increment 카운터를 생성한다.
- 카운터는 메모리(Data Dictionary)에 유지가 되고, INSERT 쿼리 처리 등 새로운 Auto Increment 값이 필요할 때마다 자신의 값을 증가시키면서 Thread에 값을 할당해 준다.
- 각 Thread가 Auto Increment 값을 받기 위해서는 SQL 구문 단위로 Auto-Inc Lock을 할당받으며, SQL 구문 처리가 완료되면 해제된다. 중복 값 할당을 방지하기 위해 Auto-Inc Lock은 테이블 레벨로 동작한다.
- Auto-Inc Lock은 테이블 레벨로 동작하므로, INSERT 비율이 매우 높거나 Bulk Insert 작업이 많다면 Auto Increment 값 처리가 DB 성능 저하의 원인이 될 수도 있다.
- 단순 INSERT 쿼리의 경우는 크게 문제가 되지 않지만, INSERT ... SELECT, LOAD DATA 와 같은 Bulk INSERT 구문의 경우 작업이 완료될 때까지 Auto-Inc Lock을 Holding 하게 되며, 다른 INSERT 구문을 처리하는 Thread는 Auto Increment 값 할당을 받지 못해 대기 상태에 들어가게 된다.
- Auto Increment 카운터 접근시 카운터가 생성되어 있지 않다면, InnoDB는 카운터 초기화 작업을 수행한다. 이 작업은 실제 "SELECT MAX(ai_col) FROM t FOR UPDATE" 쿼리를 수행하여 할당할 번호를 구하는 작업이다. 빈 테이블이라면 카운터는 1로 초기화 된다.
- 초기화 작업으로 인해 발생할 수 있는 문제는 MyISAM과는 다르게 한번 할당된 Auto Increment 값이 삭제가 된 후 MySQL이 재시작 되었다면 이 값이 재활용될 수도 있다는 점이다.
- InnoDB 엔진을 사용하는 테이블에서 Auto Increment 값 할당이 필요한 INSERT 쿼리가 수행되는 경우, 각 세션은 번호 할당을 위해 Data Dictionay에 존재하는 카운터에 접근을 하게 된다. 하지만 이 번호 할당 과정은 테이블 레벨로 배타적(Exclusive)이기 때문에, Auto Increment 번호 할당 과정이 INSERT 쿼리 성능의 병목이 될 수 있다.
- MySQL 5.0 버전에서는 SQL 구문 단위로 Auto-Inc Lock이 설정되고, 쿼리 처리가 완료된 후에 Auto-Inc Lock 해제가 발생하기 때문에 매우 큰 성능 저하가 발생하게 되는데, 이 문제는 5.1.22 버전에서 Auto Increment 카운터에 접근할 때만 Light weight mutex를 사용하도록 개선이 되었다.

출처 : http://seuis398.blog.me/70066584676

