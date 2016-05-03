#singleton
- 프로젝트 진행시 어플리케이션 전 영역의 걸쳐 하나의 클래스의 단 하나의 인스턴스만을 생성하는 것을 싱글톤 패턴이라고 한다.
- 보통 객체 생성 시 new 키워드를 사용하여 객체화 한다.
- 객체를 생성하게 되면 그 클래스의 인스턴스는 Heap 메모리에 올라가게 되고 그 인스턴스를 가리키고 있는 변수는 Stack 메모리 영역에 생기게 된다. 이러한 작업 자체가 시간이 걸리는 일이며 한 객체를 여러번 new하게 되면 시간이 더욱 오래 걸리게 된다.
- 자주 사용되는 객체는 한번만 생성하고 Heap에 존재하는 이 객체를 가르키도록만 만든다.
- 객체가 생성될 때 Heap 영역에 올라가는 시간과 메모리를 줄일 수 있다.

###문제점
- 싱글톤을 전역변수로 사용하는 경우가 많다.
- 멀티스레드에서 객체가 2개가 생성될 수 있다.


###이른 초기화
````java
public class Singleton {
    private static final Singleton instance = new Singleton();
  
    private Singleton() {}
  
    public static Singleton getInstance() {
        return instance;
    }
}
````
- 싱글톤 객체가 static으로 선언 되었기 때문에 해당 클래스가 클래스 로더에 의해 로딩 될 때 객체가 생성된다.
- 클래스 로더에 의해 클래스가 처음 로딩 될 때 수행 되므로 thread safe하다.
- 싱글톤 객체를 사용하든 안하든 해당 클래스가 로딩 되는 시점에 항상 싱글톤 객체가 생성되고 리소스(메모리)를 차지한다.


###늦은 초기화
````java
public class Singleton {
        private static volatile Singleton instance = null;
  
        private Singleton() {  }
  
        public static Singleton getInstance() {
                if (instance == null) {
                        synchronized (Singleton .class){
                                if (instance == null) {
                                        instance = new Singleton ();
                                }
                      }
                }
                return instance;
        }
} 
````
- 싱글톤 객체를 용하는 시점에 생성한다.
- getInstance() 호출시에 싱글톤 객체를 생성 시킨다.
- concurren는한 상황에서 getInstance() 메소드에 동시 접근이 가능하므로 싱글톤 객체의 특성인 ‘한개의 인스턴스만 생성’ 룰이 깨질 수 있다.
 - 해결방법 : synchronized 키워드를 사용해서 동시성 문제를 해결하고 객체 생성이 안되어 있을 경우에만 생성 하도록 처리한다.
- getInstance() 메소드에 synchronized를 걸어준다.
 - 메소드 전체에 synchnorized 를 걸어주기 때문에 성능상 이슈가 있다.
- double-checked locking 을 사용한다.
 - 싱글톤 객체가 null 일 경우에만 해당 싱글톤 객체에 synchronized를 거는 방법으로 성능 이슈를 해결한다.
- 사용시점까지 싱글톤 객체 생성을 미루기 때문에 사용하기 전까진 자원(메모리)을 점유하지 않는다.


###Enum
````java
public enum Singleton {
        INSTANCE;
        public void execute (String arg) {
                //perform operation here
        }
} 
````
- Enum type들은 프로그램 내에서 한번 초기화 된다.

- 참고: http://www.jpstory.net/2013/05/singleton-pattern/