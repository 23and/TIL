#Java에서 String 클래스가 왜 final or Immutable일까?

###String Pool
- Java 디자이너는 모든 종류의 Java 어플리케이션에서 많이 사용되는 데이터 타입이 String이 될 것이라고 예측했고, 그렇기 때문에 최적화가 필요했다.
- String pool에 String 리터럴을 포함하면 String 객체를 공유해, 템프러리하게 생성된 String 객체를 줄여줄 수 있다.
- 공유를 하기 위해서는 String 클래스는 Immutable class이어야 한다. 
- 서로 알 수 없는 두 영역에서 mutable 객체의 공유는 불가능하다. 

````java
String s1 = "Java";
String s2 = "Java";
````
- str1, str2 참조 변수가 동일한 String 객체를 참조한다.
- s1을 "Java"에서 "C++"객체로 변경하면 참조 변수 s2="C++"이 된다. 
- String을 immutable하게 하는 것으로, String 리터럴의 공유가 가능하게 된다. 
- String pool의 주요한 아이디어는 String을 final 또는 immutable하게 해야만 Java에서 String pool을 구현할 수 있다. 


###Security
- Java는 모든 서비스 레벨에서 보안 환경을 제공한다.
- String은 특히 전반적인 보안에 중요하다. 
- String은 다수의 Java 클래스에 매개 변수로 널리 사용되고 있다.
 - 네트워크 연결시, 호스트 및 포트
 - Java에서 파일을 읽어들이기 위한 파일, 디렉토리 경로
 - 데이터베이스 연결에 필요한 URL
- String이 immutable 하지 않는다면
 - 사용자는 시스템의 특정 파일에 대한 액세스 권한을 얻은 후 PATH의 변경이 가능하게 된다.
 - 네트워크 시스템과 데이터베이스에 연결하는 동안 String이 mutable하게 되면 보안 위협상태에 놓이게 된다. 
 - mutable String을 인수로 취하는 리플렉션에서도 보안 문제를 일으킬 수 있다.(??)


###Use of String in Class Loading Mechanism(이해 못함)
- String은 class loading mechanism에서 자주 사용된다. 
- String이 Immutable하지 않다고 하면 공격자는 이점을 이용할 수 있다.
 - java.io.Reader 등 Java 표준 클래스의 로드 요청시에 악성 com.unknown.DataStolenReader 클래스로 변경하게 할 수 있다.
- String이 final이나 Immutable함으로써 적어도 JVM은 올바른 클래스들을 로드할 수 있게 된다. 


###Multithreading Benefits
- Concurrency나 멀티 스레드는 Java의 핵심 기능이다.
- String 객체의 스레드 안전성을 고려해야한다. 
- String이 Immutable해서
 - 외부에서 동기화 필요가 없다.
 - 여러 스레드 간에 String을 공유하는 부분에서 코드를 깨끗하게 정리해 준다. 
 - 복잡하고 오류가 발생하기 쉬운 concurrency 코드를 쉽고 간단하게 해준다. 
- String은 concurrency하기 때문에 스레드간에 공유가 가능하고, 결과적으로 읽기 쉬운 코드가 된다. 


###Optimization and Performance
- 클래스를 Immutable한 경우의 장점은 클래스가 일단 생성되면 변경이 불가능하다는 점이다. 
 - 캐시 등의 많은 성능 최적화를 할 수 있다(??)
- String은 변경되지 않기때문에 String 해시 코드를 캐시한다. 
- 해시 코드의 계산은 지연(lazy)하여 수행되고 일단 생성되면 캐시된다. 
- 간단한 경우는 String 객체의 hashCode() 메소드를 처음 호출시에 해시 코드가 계산되고, 그 이후의 hashCode는 계산된 캐시 값을 반환하는것을 사용한다. 
- String은 Hashtable과 HashMap 등 Map 기반으로 해시가 자주 사용하는 경우에는 성능이 향상된다. 
- 해시 코드 캐시는 String이 자신의 내용에 의존하기 때문에 Immutable이나 final 없이는 불가능하다. 


###Pros and Cons of String being Immutable or Final in Java
- String은 HashMap과 Hashtable 같은 해시 기반 컬렉션의 키로 가장 많이 사용된다. 
- Immutable은 HashMap 키의 필수로 요구하지는 않지만, Immutable이 mutable보다 오브젝트를 사용하는 편이 더 안전하다. 
 - 만약 mutable 오브젝트의 상태가 HashMap에서 변경되는 경우 equals()와 hashCode() 메소드 변경후의 특성에 의해 영향을 받아 다시 뒤로 되돌아가는 취소가 어렵다. 
- 클래스가 Immutable한 경우 해시 기반 컬렉션내에 저장 될 때, 상태 변경의 위험은 없게 된다. 
- String은 Immutable하므로 외부에서 동기화를 고려하지 않고 스레드간에 안전하게 공유할 수 있다. 이는 동시 코드의 가독성이 높아 오류의 가능성을 줄일 수 있다. 


###Immutable 단점
- 비용이 소요된다. 
 - String은 Immutable하기 때문에 템프러리하게 사용할 객체를 많이 생성하게 되면 GC에 영향을 미친다.
 - Java 디자이너도 그 점은 인식하고 풀에 String 리터럴을 저장해 String의 GC를 줄일 수 있는 대안으로 생각해 왔다. 
 - 그러나, String 풀에서 오브젝트를 가져올 수 없는 new String()이라는 생성자를 사용하지 않고 String을 생성하도록 주의해야 한다.(??)
- 일반적인 Java 어플리케이션은 다수의 객체를 생성해 GC가 빈번하게 일어난다. 
- String 풀은 GC와 관련해서 숨겨져 있다.
 - String 풀은 Java Heap의 PermGen이라는 공간에 배치된다.
 - PermGen은 Java Heap에 비해 상당히 제한되는 영역이다. 
 - 다수의 String 리터럴은 이 공간을 즉시에 채운다.
 - 결과적으로 Java.lang.OutOfMemoryError : PermGen Space를 야기시킨다. 
 - Java 7 이상에서는 String pool은 일반적인 힙 공간으로 이동되었다. (PermGen에 비해 매우 큰 공간이다.)
- String을 final로 하면 확장성 제약이 있다.
 - 일반적인 상황에서는 거의 필요하지 않아도, 기능 확장을 위해 String을 확장할 수 없다.
 - java.lang.String 클래스를 확장할 수 없다.
- Integer, Long, Double, Float 등의 래퍼 클래스도 Immutable이고 Final이다.


- 참고 : http://www.mimul.com/pebble/default/2015/10/10/1444466677572.html