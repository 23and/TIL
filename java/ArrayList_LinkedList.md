#ArrayList vs LinkedList
- 둘다 리스트 인터페이스를 구현했다.

###ArrayList
- 원소가 배열
- int[] array
- get(index) 에 대하여 해당 원소에 바로 접근 가능하므로 O(1)
- 메모리 사용을 최적화하기 위한 어레이 크기 조절이 필요한 경우에 배열 전체를 복제하는 O(n) 이 걸린다.
- 자바는 프라이어러티 큐도 그렇지만 내부에는 Object[] 등이 있는 자료구조등이 많다, 그러므로 initial size 보다 커지면 당연히 복제할 것이고  이 경우 O(n)
- ArrayList에서 주의할 점은, list를 이터레잇 하는 도중에 원소를 빼면 concurrent modification exception이 걸린다. (다음 원소를 보고 또 보는 와중에 중간꺼를 빼면…index를 못 찾으니깐.)
 - 보완하는 방법 : array를 앞에서 부터 빼고, 다시 뒤에다 붙이면서 array를 본다?

###LinkedList
- 원소들이 노드
- Node {int data; Node prev; Node next;}
- 해당 노드까지 링크를 타고 가야하므로 O(n) 이 걸린다.
- add() 와 remove() 시 해당 노드를 생성하거나 없애고 링크를 수정하면 되기에 O(1) 으로 상대적으로 빠르다.