#transient

- 스트림에 데이터를 기록할 때 직렬화하고 싶지 않은 필드가 직렬화할 수 있는 객체 안에 있으면 해당 필드 선언 위에 transient 키워드를 적용할 수 있다.
- 직렬화 대상에서 제외시키고 싶은 인스턴스 변수가 있다면 transient로 선언하면 된다.
- transient를 적용한 필드는 역직렬화될 때 null을 반환한다.
- 예) private 필드를 캐시로 사용할 때 역직렬화하는 작업
 - 캐시를 간단히 재생성할 수 있다.
- 다른 필드에서 생성된 필드처럼 역직렬화한 후에 데이터가 재생성될 때도 transient를 적용한다.
- Transient variables cannot be serialized. During serialization process,
transient variable states will not be serialized. State of the value will
be always defaulted after deserialization.