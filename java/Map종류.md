#Java Map
Map�ڷᱸ���� ����ؾ��� ���� �־ Java API���� �����ϴ� Map�� ������ �˾ƺô�.
�׵��� HashMap�� ����غôµ�, ��Ȳ�� ���� Ư¡�� �´� Map�� ����ؾ߰ڴ�.

###HashMap
- ���������� Entry<K,V>[] Entry �� array �� �Ǿ� �ִ�. �ش� array �� index �� ���� �ؽ� �Լ��� ���� ���ȴ�.
- String �� sun.misc.Hashing.stringHash32 �Լ��� ����ϰ� �Ϲ� Object�� ���� hashcode �Լ��� ��Ʈ�������� ���Ǿ�����.
- ���� hash ���� ���� Ű������ �������Ƿ� Ư�� ��Ģ���� ��µȴ�.
- �˻� ������ ���� O(1) 

###TreeMap
- ���������� RedBlack Tree�� ����ȴ�.
- Map�� Ư¡�� ��ӹް� ���� �� ���������� key�� �����Ͽ� �����Ѵ�
- Ű���� ���� Compartor �������� ���� ������ �ٲܼ� �ִ�.
- Ű���� ���ĺ� ������� ���ĵȴ�. Ʈ���� ����ǹǷ� Ű���� ���� �������� ���ĵ� ���·� ��µȴ�.
- TreeMap -- implements --> NavigableMap -- extends --> SortedMap -- extends --> Map
- HashMapó�� �񵿱�ȭ(not synchronized)�Ǿ� �ִ�.
- Collections.synchronizedSortedMap �޼ҵ带 �̿��� wrapped�ؼ� SortedMap m = Collections.synchronizedSortedMap(new TreeMap(...));
- Ű���� ������ ���ش�� iterate �Ϸ��� �Ѵٸ� TreeMap�� ����. ���� ���ٿ� ���ؼ��� O(logn) ������ ���ϹǷ� ���� �����͸� ������� ���� ���� ������ ���ü�

###LinkedHashMap
- ��ũ�� ����Ʈ�� �����
- Ű���� �Է� ������� ��µǾ ���´�.
- �Է� ������ �ǹ��ִٸ� LinkedHashMap �� ����Ѵ�. ���� ���ٿ� ���� O(n) ������ ���ϹǷ� ���� �����͸� �Է��� ��� ������� �ʴ°��� ����.
- removeEldestEntry() ���� ������ ����ϰ�, LinkedHashMap �� ������ ���� ������ ���� eldest�� �˰� �ִ�.
````java
protected boolean removeEldestEntry(Map.Entry<K,V> eldest){
	return false;
}
````

- ���� : http://rangken.github.io/, http://alecture.blogspot.kr/2012/11/treemap.html, http://blog.naver.com/kiho0530/150138013167