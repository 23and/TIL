#table space 단편화
- Oracle에서 다량의 데이터 insert, delete 시 블럭의 수가 증가한다.
- HWM(High Water Mark)도 증가한다.
- full table scan 할 경우 수행 성능을 고려하야 HWM까지 데이터를 추출하기 때문에 불필요한 IO가 일어난다.
- 사용하지 않는 빈 블럭들을 없애고, 데이터를 한곳으로 모아야 한다. (HWM를 낮추기 위해서)
- 대부분의 마스터 테이블들은 생성될 때 저장공간이 할당되지만, 모두 사용되지 않으며, 이런 빈공간은 디스크를 불필요하게 낭비하게 되기 때문에 다음 수행 문장을 통해 디스크로 반환시킬 수 있다.
````
ALTER TABLE 테이블명 DEALLOCATE UNUSED;
````