#스레드 이용하기
- 애플리케이션이 실행되려면 최소한 하나의 스레드는 있어야한다.
- 새로운 스레드를 만들 때마다 코드는 해당 스레드에서 즉시 실행된다.
- 싱글코어 CPU에서 하나 이상의 코드를 한꺼번에 실행하는 건 물리적으로 불가능하다.
- JVM은 스레드를 관리하고 어떤 스레드를 언제 처리하는지 결정해야한다.
- Thread객체의 start 메서드를 호출한 후에는 run메서드를 호출해서 JVM에서 코드를 실행하는 데 필요한 새로운 스레드를 생성한다.
- Thread 클래스는 병렬 실행이 가능한 스레드를 만들 수 있도록 JVM을 호출한다.
- 모든 자바 객체는 스스로 락을 유지할 수 있다.
- synchronized(object) 코드를 감싸서 한 번에 스레드 하나만 코드 블록 안에서 실행할 수 있게 한다.
- 병렬 실행은 어디서 어떻게 실행 중인 스레드들이 만나는지 항상 불분명하므로 다른 블록의 코드들 사이의 상호작용을 이해하는 것이 중요하다.


###프로세스
- 실행중인 프로그램
- 프로그램을 실행하면 프로세스이다.
- 프로세스는 프로그램을 수행하는데 필요한 데이터와 메모리 등의 자원과 스레드로 구성되어있다.
- 프로세스의 자원을 이용해서 실제로 작업을 수행하는 것이 스레드이다


###스레드
- 한번 사용된 스레드는 다시 재사용될 수 없습니다. 즉 하나의 스레드에 대해 start()는 한번만 호출된다.
- start()를 호출하면 생기는 일
 - 새로운 스레드가 작업을 실행하는데 필요한 호출스택을 생성한 다음에 run을 호출해서 생성된 호출스택에 run이 첫 번째로 저장되게 한다.
- 모든 스레드는 독립적인 작업을 수행하기 위해 자신만의 호출스택을 필요로 한다.
- 두 개의 스레드로 작업하는 것이 싱글스레드보다 시간이 더 걸릴 수 있는 이유는?
 - 스레드 간의 작업전환시간 때문에
- 스레드의 우선순위가 높아야하는 작업에는 무엇이 있을까?
 - 파일전송기능이 있는 메신저의 경우 파일다운로드처리 스레드보다 채팅내용을 전송하는 스레드의 우선순위가 더 높아야할 것이다.
 - 시각적인 부분이나 사용자에게 빠르게 반응해야하는 작업을 하는 스레드
- 스레드에 우선순위를 부여하는 방법
 - setPriority(우선순위)
 - 우선순위 범위는1~10이며 숫자는 상대적인 크기이다.
- 스레드의 상태 NEW RUNNABLE BLOCKED WAITING,TIMED_WAITING TERMINATED
 - NEW 스레드가 생성되고 아직 START()가 호출되지않은상태
 - RUNNABLE 실행 중 또는 실행 가능한 상태
 - BLOCKED 동기화블럭에 의해서 일시정지된 상태
 - WAITING,TIMED_WAITING 스레드의 작업이 종료되지는 않았지만 실행가능하지 않은 일시정지 상태 TIMED_WAITING은 일시정지시간이 지정된 경우
 - TERMINATED 스레드의 작업이 종료된 상태
- sleep와 yield는 현재 실행중인 스레드에 대해 동작한다


###스레드 상태 변화
- 스레드를 생성하고 start를 호출하면 바로실행되는 것이 아니라 실행대기열에 저장되어 자기 차례가 될 때까지 기다린다.
- 실행대기상태에서 자신의 차례가되면 실행상태가 된다
- 주어진 실행시간이 다되거나 yield를 만나면 다시 실행 대기상태가 된다
- 실행중에 suspend sleep wait join I/Oblock에 의해 일시정지상태가 될 수 있다.
- 지정된 일시정지시간이 다되거나 notify resume interrrupt가 호출되면 일시정지 상태를 벗어나고 다시 실행대기열에 저장되어 자신의 차례를 기다린다
- 실행을 모두마치거나 stop이 호출되면 스레드는 소멸한다


###스레드 실행
- Thread클래스를 상속받는 것
````java
class A extends Thread{
	public void run(){ }
}
````

- Runnable인터페이스를 구현하는 것
````java
class A implements Runnable{
	pbulic void run(){ }
}
````

- start()가 하는 일
 - 새로운 스레드가 작업을 실행하는데 필요한 호출스택을 생성한 다음 run()을 호출해서 생성된 호출스택에 run()이 첫 번째로 저장되게 한다

````java
public class ThreadEx {
	public static void main(String args[]){
		long startTime=System.currentTimeMillis();
		for(int i=0; i<300; i++){
			System.out.print("-");
		
		}
		System.out.print("소요시간"+(System.currentTimeMillis()-startTime));
		for(int i=0;i<300; i++){
			System.out.print("l");
		}
		System.out.print("소요시간2"+(System.currentTimeMillis()-startTime));
	}

}
````


- 새로운 스레드를 생성해서 두 개의 스레드가 작업을 하나씩 나누어 수행하는 코드
````java
public class ThreadEx {
	static long startTime=0;

	public static void main(String[] args) {
		ThreadEx5_1 th1=new ThreadEx5_1();
		th1.start();
		startTime=System.currentTimeMillis();
		
		for(int i=0; i<300; i++){
			System.out.println("-");
		}
		
		System.out.println("소요시간"+(System.currentTimeMillis()-ThreadEx5.startTime));

	}

}
````

````java
public class ThreadEx5_1 extends Thread {
	public void run(){
		for(int i=0; i<300; i++){
		System.out.print("l");
	}

	System.out.println("소요시간"+(System.currentTimeMillis()+ThreadEx5.startTime));
	}
}
````

###데몬스레드
- 일반스레드의 작업을 돕는 보조적인 역할을 수행하는 스레드
- 일반스레드가 종료되면 데몬스레드는 강제적으로 자동 종료된다
- ex) 가비지컬렉터, 워드프로세서의 자동저장, 화면자동갱신

###interrupt()
- sleep()이나 join()에 의해 일시정지상태인 스레드를 실행대기상태로 만든다

###join()
- 지정된 시간동안 스레드가 실행되도록한다 지정된 시간이 지나거나 작업이 종료되면 join()을 호출한 스레드로 다시 돌아와 실행을 계속한다

###멀티쓰레딩의 장점
- CPU의 사용률을 향상시킨다
- 자원을 보다 효율적으로 사용할 수 있다
- 사용자에 대한 응답성이 향상된다
- 작업이 분리되어 코드가 간결해진다

###교착상태
- 두 스레드가 자원을 점유한 상태에서 서로 상대편이 점유한 자원을 사용하려고 기다리느라 진행이 멈춰있는 상태