#String vs StringBuilder vs StringBuffer

###String
- String은 불변의 속성을 가진다.
- 문자열 객체가 생성되면 수정되지 않는다.
- 사용하지 않는 String은 가비지 컬렉션이 회수한다.

###StringBuilder
- 가변의 속성을 가진다.
- 버퍼가 부족할 경우 자동적으로 버퍼의 크기를 늘린다.
- 동기화를 보장하지 않는다.
- StringBuffer보다 조금 빠른 속도

###StringBuffer
- 가변의 속성을 가진다.
- 동기화를 보장한다.
- 멀티 스레드 환경에서 쓸 때