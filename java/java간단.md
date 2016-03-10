#Java
- equals메소드는 참조변수에 저장된 주소값이 같은지 판단한다
- 해시코드는 객체의 주소값을 이용해서 해시코드를 만들어서 반환하기 때문에 한번의 실행에서 서로다른 두 객체는 같은 해시코드를 가질 수 없다
- clone메소드를 사용하기위해서는 Coloneable 인터페이스를 구현해야한다
- 배열을 복사하는 두가지 방법 : clone()메소드, arraycopy()메소드
- 참조변수에 String을 더하면 참조변수가 가리키고있는 인스턴스의 toString()을 호출하여 String을 얻은 다음 결합한다
- String클래스는 인스턴스를 생성할 때 지정된 문자열을 변경할 수 없다.
- StringBuffer에 담긴 문자열을 비교하기 위한 방법은?
 - StringBuffer은 equals를 오버라이딩하지않았다.
 - 하지만 toString은 오버라이딩했고, 담고있는 문자열을 반환한다
 - StringBuffer에 담긴 문자열을 비교하기 위해서 SringBuffer인스턴스에 toString을 호출해서 Sting인스턴스를 얻은다음 여기에 equlas메소드를 사용해서 비교한다
- 기본형 변수를 객체로 다루기 위해 사용하는 클래스 : wrapper
- 내부클래스란 클래스내에 선언된 클래스이다.두 클래스가 긴밀한 관계에 있을 때 사용한다. 내부클래스에서 외부클래스의 멤버들을 쉽게 접근할 수 있고 코드의 복잡성을 줄일 수 있다
- 지역클래스에서 사용할 수 있는 멤버는 무엇이 있는가? 외부클래스의 인스턴스멤버,static멤버,final이 붙은 지역클래스가 포함된 메소드에 정의된 지역변수
- 이 코드의 출력 값은? **30 20 10**
```java
class Outer {
	int value=10;				

	class Inner {
		int value=20;	
		void method1() {
			int value=30;
			System.out.println(value);
			System.out.println(this.value);
			System.out.println(Outer.this.value);
		}
	} // Inner클래스의 끝
} // Outer클래스의 끝

class InnerEx5 {
	public static void main(String args[]) {
		Outer outer = new Outer();
		Outer.Inner inner = outer.new Inner();
		inner.method1();
	}
} // InnerEx5 끝
```

- 익명클래스는 이름이 없는 클래스로 클래스의 선언과 객체의 생성을 동시에 하기 때문에 단 한번만 사용할 수 있고, 하나의 객체만 생성할 수 있는 일회용 클래스이다
- List 순서가 있는 데이터의 집합, 데이터의 중복을 허용한다
- Set 순서를 유지하지 않는 데이터집합, 데이터의 중복을 허용하지 않는다
- Map 키와 값의 쌍으로 이루어진 데이터 집합. 순서는 유지되지않으며 키는 중복을 허용하지않고 값은 중복을 허용한다.
- Vector와 Hashtable은 기존 컬렉션 클래스의 호환을 위해 남겨었지만 ArrayList와 HashMap으로 사용하는 것이 좋다
