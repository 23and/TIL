#final
- 기본적으로 한번 정의된 뒤에는 변경이 불가능함을 의미하는 키워드이다.
- 변수의 앞에 붙는 경우 해당 변수는 정의 된 뒤, 맨 처음에 할당 한 값을 변경 시킬 수 없다. 
- 정의만하고 아직 할당을 하지 않은 Final 변수는 Blank Final 변수라한다.
- 할당 한 값이 reference 라면 해당 reference 는 변경이 될 수 없으나 reference 된 object 의 내부는 변경이 가능하다.
````java
final List l = new ArrayList();
````
- l = new List(); 는 불가능하여 compile-time error 가 일어나지만, l.add(obj); l.remove(index); 등의 동작은 가능하다.
- 상수의 경우 (즉 static + final) 와 다르게 instance &e final variable 은 compile time 에 compiler 가 값을 알 필요가 없으며, 일반적으로 회사가 정의한 rule에 의해서 이름을 만든다.
- 클래스 앞에 Final 이 붙는 경우, 해당 클래스는 sub class 를 만들 수 없다. (즉, extends 불가) 
- 암묵적으로 해당 클래스 내의 모든 메소드 역시 Final 메소드가 되어 override 혹은 hidden 될 수 없다. 
- 보안과 효율성으로 인해 많은 자바의 기본 라이브러리 클래스들은 Final 이다.

- 참고 : crack-tech-interview.com