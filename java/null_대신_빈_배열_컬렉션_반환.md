#null대신 빈 배열이나 컬렉션 반환

````java
public Cheese[] getCheeses(){
	if(cheesesInStock.size() == 0){
	return null;
	}
}
````
- 위와 같이 치즈 재고가 없는 상황을 특별하게 처리하도록 강제하는 코드는 바람직하지 않다.
- 클라이언트 입장에서는 null이 반환될 때를 대비한 코드를 만들어야 한다.
- 클라이언트가 null처리를 잊어버릴 수 있기 때문에
- 빈 배열이나 컬렉션 대신 null을 반환하는 메서드는 구현하기 더 까다롭다.
- 배열 할당 비용을 피알 수 있으니 null 반환하는 것이 바람직한 것 아니냐
 - no
 - 프로파일링 결과로 해당 메서드가 성능 저하의 주범이라는 것이 밝혀지지 않은 한 그런 수준까지 성능 걱정을 하는 것은 바람직 하지 않다.
 - 길이가 0인 배열은 변경이 불가능하므로 아무 제약 없이 재사용할 수 있다.
````java
//컬렉션에서 배열을 만들어 반환하는 올바른 방법
private final List<Cheese> cheesesInStock = ...;
private static final Cheese[] EMPTY_CHEESE_ARRAY = new Cheese[0];

//@return 재고가 남은 모든 치즈 목록을 배여롤 만들어 반환
public Cheese[] getCheeses(){
	return cheesesInStock.toArray(EMPTY_CHEESE_ARRAY);
}
````
- toArray 메서드에 전달되는 빈 배열 상수는 반환값의 자료형을 명시한다.
- 보통 toArray는 반환되는 원소가 담길 배열을 스스로 할당하는데, 컬렉션이 비어 있는 경우에는 인자로 주어진 빈 배열을 쓴다.