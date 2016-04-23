#Java Map
Map자료구조를 사용해야할 일이 있어서 Java API에서 제공하는 Map의 종류를 알아봤다.
그동안 HashMap만 사용해봤는데, 상황에 따라서 특징에 맞는 Map을 사용해야겠다.

###HashMap
- 내부적으로 Entry<K,V>[] Entry 의 array 로 되어 있다. 해당 array 에 index 는 내부 해쉬 함수를 통해 계산된다.
- String 은 sun.misc.Hashing.stringHash32 함수를 사용하고 일반 Object는 내부 hashcode 함수와 비트연산으로 계산되어진다.
- 내부 hash 값에 따라서 키순서가 정해지므로 특정 규칙없이 출력된다.
- 검색 성능이 좋다 O(1) 

###TreeMap
- 내부적으로 RedBlack Tree로 저장된다.
- Map의 특징을 상속받고 저장 시 내부적으로 key를 정렬하여 저장한다
- 키값에 대한 Compartor 구현으로 정렬 순서를 바꿀수 있다.
- 키값이 알파벳 순서대로 정렬된다. 트리에 저장되므로 키값은 일정 기준으로 정렬된 상태로 출력된다.
- TreeMap -- implements --> NavigableMap -- extends --> SortedMap -- extends --> Map
- HashMap처럼 비동기화(not synchronized)되어 있다.
- Collections.synchronizedSortedMap 메소드를 이용해 wrapped해서 SortedMap m = Collections.synchronizedSortedMap(new TreeMap(...));
- 키값이 일정한 수준대로 iterate 하려고 한다면 TreeMap이 좋다. 랜덤 접근에 대해서는 O(logn) 성능을 지니므로 많은 데이터를 넣을경우 좋지 않은 성능이 나올수

###LinkedHashMap
- 링크드 리스트로 저장됨
- 키값은 입력 순서대로 출력되어서 나온다.
- 입력 순서가 의미있다면 LinkedHashMap 을 사용한다. 랜덤 접근에 대해 O(n) 성능을 지니므로 많은 데이터를 입력할 경우 사용하지 않는것이 좋다.
- removeEldestEntry() 들어온 순서를 기억하고, LinkedHashMap 에 들어온지 가장 오래된 값을 eldest로 알고 있다.
````java
protected boolean removeEldestEntry(Map.Entry<K,V> eldest){
	return false;
}
````

- 참고 : http://rangken.github.io/, http://alecture.blogspot.kr/2012/11/treemap.html, http://blog.naver.com/kiho0530/150138013167