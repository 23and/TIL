###Quartz
- http://www.quartz-scheduler.org/documentation
- Scheduling 서비스는 어플리케이션 서버 내에서 주기적으로 발생하거나 반복적으로 발생하는 작업을 지원하는 기능으로서 유닉스의 크론(Cron) 명령어와 유사한 기능을 제공한다.
- 실행환경 Scheduling 서비스는 오픈소스 소프트웨어로 Quartz 스케쥴러를 사용한다. 
- Quartz는 오픈 소스 작업 스케줄링 프레임워크이다.
- Job으로 사용할 클래스는 반드시 org.quartz.Job 인터페이스를 구현하고, Job 인터페이스가 가지고 있는 public void execute(JobExecutionContext context) 메소드를 정의해 주어야 한다.
- SimpleTrigger : interval, delay, repeat times등을 설정한다.
- CronTrigger : cron 표현법을 사용하여 스케줄링 기능을 제공한다. 작업(Job) 실행이 달력 개념을 기반으로 반복된다면 SimpleTrigger보다 CronTrigger가 더 유용하게 사용될 수 있다.

- Expression Meaning
	0 0 12 * * ?				매일 12시(정오)
	0 15 10 ? * *				매일 오전 10시 15분
	0 15 10 * * ?				매일 오전 10시 15분
	0 15 10 * * ? *				매일 오전 10시 15분
	0 15 10 * * ? 2005			2005년에 매일 아침 10시 15분
	0 * 14 * * ?				매일 오후 2시 0분 ~ 59분
	0 0/5 14 * * ?				매일 오후 2시부터 2시 55분까지 5분마다
	0 0/5 14,18 * * ?			매일 오후 2시부터 2시 55분까지 5분마다, 6시부터 6시 55분까지 5분마다
	0 0-5 14 * * ?				매일 오후 2시부터 2시 5분까지 매분
	0 10,44 14 ? 3 WED			매년 3월의 수요일마다 오후 2시 10분과 2시 44분
	0 15 10 ? * MON-FRI			월요일부터 금요일까지 오전 10시 15분
	0 15 10 15 * ?				매달 15일 오전 10시 15분
	0 15 10 L * ?				매달 마지막 날 오전 10시 15분
	0 15 10 ? * 6L				매달 마지막 금요일 오전 10시 15분
	0 15 10 ? * 6L 2002-2005	2002년부터 2005년까지 매달 마지막 금요일 오전 10시 15분
	0 15 10 ? * 6#3				매달 3번째 금요일 오전 10시 15분
	0 0 12 1/5 * ?				매달 첫날부터 5일마다 12시(정오)
	0 11 11 11 11 ?				매년 11월 11일 오전 11시 11분

###@Scheduled annotation
- value : cron, fixedDelay, fixedRate 트리거
- @Scheduled 부여되는 메소드는 파라미터를 가질 수 없고, void형 리턴타입을 가진다.
- @Scheduled(cron=표현) : 크론탭 설정
- @Scheduled(fixedDelay=1000) : 이전에 실행된 Task의 종료시간으로부터 일정시간만큼 지난 후 실행한다.
- @Scheduled(fixedRate=1000) : 이전에 실행된 Task의 시작시간으로 부터 정의된 시간만큼 지난후 실행한다.

	
###Spring Batch
- 배치처리란 인간의 상호 작용이 없이 컴퓨터에서 동작하는 프로그램('Job')의 일련의 실행이다.
- 사용자와의 상호작용이 없다.
- 주로 Time based event에 의해 실행된다.
- 에러처리, 복구, 모니터링, 유지보수가 쉬운 구조이여야 한다.

#####Spring Batch 장점
- 대용량 배치에 맞는 읽기방식과 Transaction처리를 간단히 구현할 수 있다.

#####Spring Batch 기능
- Job Repository를 통한 배치 모니터링
- 배치에 적합한 트랜잭션 처리를 위해 주기적인 commit방식 지원한다.
- 배치작업의 재시도, 재시작, 건너뛰기 등의 정책을 설정으로 적용 가능하다.
- Commit 수, Rollback 수, 재시도 횟수 등 배치실행 통계 정보를 제공한다.

  
#####배치 구조
- Run Tier
  -> Application의 scheduling, 실행을 담당한다.
  -> 스프링배치는 따로 Scheduling의 기능은 제공하지 않는다.
  -> Quartz나 Cron을 이용하도록 권고.

- Job Tier
  -> 전체적인 Job의 수행을 책임진다.
  -> Job내의 각 Step들을 정책에 따라 순차적으로 수행한다.

- Application Tier
  -> Job을 수행하는데 필요한 component

- Data tier
  -> Database, File등 물리적 데이터소스
  
- 큰 범주 <————-------------> 작은 범주
- 업무 – batch – step – RPW – 세부 logic

- ItemReader
 -> reader.open() 에서 쿼리를 호출 해 (혹은 파일을 읽어) 처리할 data set을 읽어들이는 역할을 한다. 읽은 데이터를 read()를 통해 건별로 Processor 객체로 넘긴다.

- ItemProcessor
 -> Processor.process()에서 read()로 부터 읽은 데이터를 매개변수로 받아 업무 로직에 따라 처리한다. Open에서 읽은 data set이 n개의 row라고 할 때 Processor.process()는 n번 수행된다.

- ItemWriter
  -> Processor에서 처리한 데이터를 적재하기위해 DML을 수행한다. 물론, 경우에 따라 java 구현없이 xml상에서 코딩 된 sync sort를 수행하거나, .sam file 을 떨군다거나 DML처리를 위해 write()를 직접 구현할 수도 있다.


#####배치 구성요소
- JobLauncher
  -> JobLauncher는 배치 Job을 실행시키는 역할을 한다.
  -> Job과 Parameter를 받아서 실행. JobExecution를 반환 한다.

- Job
  -> 실행시킬 작업을 의미, 논리적인 job 실행의 개념, job configuration과 대응되는 단위.
  
- JobParameter
  -> 배치 job을 시작하는데 사용하는 파라미터의 집합으로 job이 실행되는 동안에 job을 식별하거나 job에서 참조하는 데이터로 사용한다.

- JobInstance
  -> 논리적인 Job 실행
  -> JobInstance=Job+JobParameter
  
- JobExecution
  -> 단 한 번 시도되는 Job 실행을 의미하는 기술적인 개념
  -> 시작시간, 종료시간 ,상태(시작됨,완료,실패),종료상태의 속성을 가진다.

- JobRepository
  -> 수행되는 Job에 대한 정보를 담고 있는 저장소.
  -> 어떠한 Job이 언제 수행되었고, 언제 끝났으며, 몇 번이 실행되었고 실행에 대한 결과가 어떤지 등의 Batch수행과 관련된 모든 meta data가 저장되어 있다.

- Step
  -> Batch job을 구성하는 독립적인 하나의 단계
  -> Job은 하나이상의 step으로 구성한다.
  -> 실제 배치 처리 과정을 정의하고, 제어하는데 필요한 모든 정보를 포함한다.

- Step Execution
  -> 하나의 step을 실행하는 한번의 시도.
  -> 시작시간, 종료시간,상태, 종료상태, commitCount, itemCount 의 속성을 가진다.

- Item
  -> 처리할 데이터의 가장 작은 구성 요소.

- ItemReader
  -> Step안에서 File 또는 DB등에서 Item을 읽어 들인다.
  -> 더 이상 읽어올 Item이 없을 때에는 read()메소드에서 null값을 반환. 그 전까지는 순차적인 값을 리턴

- ItemWriter
  -> Step안에서 File 또는 DB등으로 Item을 저장한다.

- Item Processor
  -> Item reader에서 읽어 들인 Item에 대하여 필요한 로직처리 작업을 수행한다.

- Chunk
  -> 하나의 Transaction안에서 처리할 Item의 덩어리.
  -> chunk size가 10이라면 하나의 transaction안에서 10개의 item에 대한 처리를 하고 commit을 하게 되는 것이다.

출처 : http://wiki.gurubee.net/pages/viewpage.action?pageId=4949437, http://bcho.tistory.com/763

