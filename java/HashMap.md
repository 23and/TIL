#HashMap

- void clear() : HashMap 의 모든 요소를 삭제한다.
- boolean containsKey(Object key) : 지정된 키(Key)를 포함하고 있으면 true 값을 리턴한다.
- boolean containsValue(Object value) : 하나 이상의 키를 지정된 값(value)에 매핑시킬 수 있으면 true 값을 리턴한다.
- V get(Obect key) : 지정된 키(key)에 매핑되는 값을 리턴한다.  키에 매핑되는 어떤 값도  없으면 NULL 값을 리턴한다.
- boolean isEmpty() : HashMap이 비어있으면 true 값을 리턴한다.
- Set<K> keySet() : HashMap에 있는 모든 키를 담은 Set<K> 의 켈럭션을 리턴한다.
- V put(K key, V value) : key 와 value를 매핑하여 HashMap에 저장한다.
- V remove(Object key) : 지정된 키(key)와 이에 매핑된 값을 HashMap에서 삭제 한다.
- int size() : HashMap에 포함된 요소의 개수를 리턴한다.

### Value값으로 정렬
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

- 참고 : http://www.programcreek.com/2013/03/java-sort-map-by-value/
