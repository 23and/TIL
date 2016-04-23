#HashMap

- void clear() : HashMap �� ��� ��Ҹ� �����Ѵ�.
- boolean containsKey(Object key) : ������ Ű(Key)�� �����ϰ� ������ true ���� �����Ѵ�.
- boolean containsValue(Object value) : �ϳ� �̻��� Ű�� ������ ��(value)�� ���ν�ų �� ������ true ���� �����Ѵ�.
- V get(Obect key) : ������ Ű(key)�� ���εǴ� ���� �����Ѵ�.  Ű�� ���εǴ� � ����  ������ NULL ���� �����Ѵ�.
- boolean isEmpty() : HashMap�� ��������� true ���� �����Ѵ�.
- Set<K> keySet() : HashMap�� �ִ� ��� Ű�� ���� Set<K> �� �̷����� �����Ѵ�.
- V put(K key, V value) : key �� value�� �����Ͽ� HashMap�� �����Ѵ�.
- V remove(Object key) : ������ Ű(key)�� �̿� ���ε� ���� HashMap���� ���� �Ѵ�.
- int size() : HashMap�� ���Ե� ����� ������ �����Ѵ�.

### Value������ ����
````java
public class SortHashMapValues {
	public static void main(String[] args) {
		Map<String, Integer> map = new HashMap<String, Integer>();
		map.put("one", 1);
		map.put("ten", 10);
		map.put("three", 3);
		map.put("two", 2);

		List list = new ArrayList(map.entrySet());

		Collections.sort(list, new Comparator() {
			public int compare(Object obj1, Object obj2) {
				return ((Comparable) ((Map.Entry) (obj1)).getValue()).compareTo(((Map.Entry) (obj2)).getValue());
			}
		});
		System.out.println(list);
	}
}
````

- ���� : http://www.programcreek.com/2013/03/java-sort-map-by-value/
