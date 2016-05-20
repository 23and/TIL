#dynamic array resizing

- 배열은 크기를 지정해서 생성한다.
- 배열 크기보다 더 큰 데이터 저장이 필요한 경우에는 새로 배열을(큰 사이즈로) 생성하고, 기존 내용을 복사해서 사용한다.
- 데이터 크기를 알 수 없는 경우 배열은 적절하지 않을 수 있다. 이런 경우 보통 LinkedList를 사용한다.
 - 실제 데이터보다 큰 배열을 생성하면 메모리를 낭비할 수 있다.
 - 배열 사이즈보다 더 큰 데이터가 들어와서 다시 배열을 생성하고 복사해야할 수 있다.
- 이론적으로는 위와같이 알고있었는데, java Map클래스에서 array resize를 사용한다. 왜 그런지는 잘 모르겠다. (알게되면 수정해야지)

````java
void More addEntry(int hash, K key, V value, int bucketIndex) {
	Entry<K,V> e = table[bucketIndex];
	table[bucketIndex] = new Entry<K,V>(hash, key, value, e);
	if (size++ >= threshold)
	resize(2 * table.length);
}
````
출처 : http://bcho.tistory.com/, http://grepcode.com/file/repository.grepcode.com/java/root/jdk/openjdk/6-b14/java/util/HashMap.java#HashMap.addEntry%28int%2Cjava.lang.Object%2Cjava.lang.Object%2Cint%29