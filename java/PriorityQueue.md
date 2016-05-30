#PriorityQueue

- java.util
````java
PriortyQueue<E>() //기본 생성자를 이용해서 생성
PriorityQueue<E>(int initialCapacity, Comparator<? super E> comparator) //초기 큐 내부의 배열 크기와 Comparator 객체를 전달하면서 객체를 생성
````
- 우선순위 큐는 요소를 무작위로 삽입해도 정렬된 순서로 꺼낸다.
- remove 메서드를 호출할 때마다 우선순위 큐에서 현재 가장 작은 요소를 가져온다.
- 우선순위 큐는 보통 작업 스케줄링에 사용된다. 
 - 작업에는 우선순위가 있고, 작업은 무작위로 추가된다.
 - 새로운 작업을 시작할 수 있을 때마다 큐에서 우선순위가 가장 높은 작업을 제거한다.
 - 우선순위는 1이 가장 높으므로 remove 연산은 최소값 요소를 돌려준다.
- 우선순위 큐는 Comparable 인터페이스를 구현하는 클래스의 요소를 저장할 수 있다. 또는 생성자에 Comparator를 전달할 수 있다. 하지만 요소를 순회할 때 꼭 정렬된 순서로 돌려주지는 않는다.
````java
public class Job implements Comparable<Job> { ... }
PrioriyQueue<Job> jobs = new PriorityQueue<>();
jobs.add(new Job(4, "Collect garbage"));
jobs.add(new Job(9, "Match braces"));
jobs.add(new Job(1, "Fix memory leak"));

while(jobs.size() > 0) {
  Job job = jobs.remove();
  excute(job);
} 
````
###initialCapacity
- 큐 내부에서 사용하는 배열의 초기 크기를 결정하는 값이다.
- 기본적으로 11의 크기를 사용하고 임의로 전달할 경우에는 그 크기를 사용하는데 1보다 작은 경우 IllegalArgumentException 예외가 발생한다.
- 배열의 크기는 initialCapacity로 고정되는 것이 아니라, 요소의 수가 배열의 크기에 도달하면 크기를 늘린다. 
- 배열의 크기가 커질 때 규칙을 보면 배열의 크기가 64 미만일 때는 2씩 커지고, 그 이후로는 이전 크기의 1/2 씩 증가하도록 되어있다.
- 큐 내의 배열의 최대크기는 private static final int MAX_ARRAY_SIZE = Integer.MAX_VALUE - 8;

- 출처 : http://nnoco.tistory.com/66, http://blog.naver.com/PostView.nhn?blogId=horajjan&logNo=220584925837