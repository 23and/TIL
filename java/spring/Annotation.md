#Annotation
@Autowired
- 의존 관계를 자동으로 설정할 때 사용한다.
- 생성자, 필드, 메서드의 세 곳에 적용이 가능하다.
- 스프링은 필드, 메서드, 생성자 등에 @Autowired 적용되어 있으면, 해당하는 타입의 스프링 빈 객체를 알맞게 연결해준다.
- 필드에 적용하면 의존 객체를 전달받기 위한 메서드를 추가하지 않아도 된다. 
- 스프링은 @Autowired 어노테이션을 발견하면, @Autowired에 해당하는 스프링 빈 객체를 찾아서 설정한다. 
- @Autowired에 해당하는 타입의 빈 객체가 존재하지 않으면 스프링은 컨테이너를 초기화하는 과정에서 예외를 발생시킨다.
- @Autowired을 적용은 했지만, 스프링 빈이 존재하지 않는 경우에 예외를 발생시키지 않고, null로 값을 유지하고 싶을 수도 있때
  -> @Autowired의 required 속성 값을 false로 지정하면 된다. 
  -> required 속성 값이 false일 경우, 스프링은 일치하는 스프링 빈이 존재하지 않더라도 예외를 발생시키지 않는다.

@RestController  
- view가 필요없는 API만 지원하는 서비스에서는 @RestController를 쓴.
- view가 필요한 곳에서 @RestController를 사용해서 클래스를 매핑하면, view로 접근을 못하는 문제가 있다.
  -> @RestController가 @ResponseBody를 포함하고 있기 때문이다.
- view가 필요하고, 해당 클래스에서 restfulAPI와 view를 함께 사용하고 싶은 경우에는 클래스에 @Controller로 지정해주고,
  restfulAPI에는 @ResponseBody를 일일히 붙여주도록 사용을 해야 한다.

@Configuration
- java 클래스가 spring 환경 설정과 관련된 파일이라는 것을 알려준다.
- @Bean 어노테이션을 함수 위에 언급하면, spring에서 사용하는 bean을 리턴해준다.
- @Configuration 어노테이션으로 설정한 클래스는 Spring에서 사용하는 Bean 자체로도 인식된다.
- @Configuration어노테이션을 사용한 클래스에서 @Bean어노테이션을 사용한 함수가 리턴하는 객체는 자체적으로 Singleton으로 관리해준다.

@Value
- 변수에 값을 초기화하기 위해 사용한다

@Transactional
- 속성
  -> propagation : 트랜잭션 전파 규칙을 설정. Propagation 열거형 타입에 값이 정의되어 있음. 기본값은 Propagation.REQUIRED
  -> isolation : 트랜잭션 격리 레벨을 설정. Isolation 열거형 타입에 값이 정의되어 있음
  -> readOnly : 읽기 전용 여부를 설정. boolean 값을 설정하며, 기본값은 false
  -> rollbackFor : 트랜잭션을 롤백할 예외 타입을 설정. ex) rollbackFor={Exception.class}
  -> noRollbackFor : 트랜잭션을 롤백하지 않을 예외 타입을 설정. ex) noRollbackFor={ItemNotFoundException.class}
  -> timeout : 트랜잭션의 타임아웃 시간을 초 단위로 설정
  
@Scheduled
- value : cron, fixedDelay, fixedRate 트리거
- @Scheduled 부여되는 메소드는 파라미터를 가질 수 없고, void형 리턴타입을 가진다.
- @Scheduled(cron=표현) : 크론탭 설정
- @Scheduled(fixedDelay=1000) : 이전에 실행된 Task의 종료시간으로부터 일정시간만큼 지난 후 실행한다.
- @Scheduled(fixedRate=1000) : 이전에 실행된 Task의 시작시간으로 부터 정의된 시간만큼 지난후 실행한다.

@Valid
- @AssertFalse :  거짓 확인
- @AssertTrue : 참 확인
- @DecimalMax : 지정 값 이하의 실수 확인
- @DecimalMin : 지정 값 이상의 실수 확인
- @Digits(integer=, fraction= ) : 정수 여부
- @Future : 미래 날짜 확인
- @Max : 지정 값 이상 확인
- @Min :  지정 값 이하 확인
- @NotNull : Null이 아닌지 확인
- @Null : Null 확인
- @Pattern(regex=, flag) : 정규식 확인
- @Past : 과거 날짜 확인
- @Size(min=, max=) : 문자열 배열의 길이 만족 여부
- BindingResult bindingResult
