#java 숫자 비교
- int
 - Primitive 자료형 (long, float, double,. ....)
 - 자료형
 - 산술 연산이 가능. 
 - null 로 초기화 불가능, 0으로 초기화

- Integer 
 - Wrapper 클래스(객체)
 - 클래스
 - Unboxing 을 하지 않으면 산술 연산이 불가능하지만, null값은 처리할 수 있음.
 - null값 처리가 용이해서 SQL 과 연동할 경우 처리가 용이. 직접적인 산술연산은 불가능 

- int와 Integer의 변환
````java
int i = integer.intValue();
Integer integer = new Integer(i);
````

- Boxing과 Unboxing 의 차이 
 - Boxing 자료형 : Wrapper 클래스 (Integer)
 - Unboxing 자료형 : Privimtive 자료형  (int)
 - int -> Integer 로 변환 (Auto boxing)
 - Integer -> int 로 변환 ( Auto unboxing)
 - Autoboxing은 자바 컴파일러가 primitive형과 Wrapper 클래스 사이에서 만드는 자동 변환

````
###숫자 타입 비교
````java
int a = 1;
Integer b = 1;
Integer c = new Integer(1);

if (a == 1) true 
if (b == 1) true
if (c == 1) true
````
- int vs Integer
````java
if (a == b) true
````

- int vs Integer
````java
if (a == c) true
````

- Integer vs Integer
````java
if (b == c) false
if (b.equals(c)) true
````

- 비교 대상 중 primitive type(int) 의 변수가 하나라도 있다면, == 연산자는 값으로 비교한다.
- Boxed primitive 또는 Wrapper class(Integer) 끼리 비교 하는 경우, == 연산자는 각 객체의 주소 값을 비교 하게 된다.
- 값끼리의 비교는 equal 메소드를 사용해야한다.
참고 : marobiana.tistory.com, egloos.zum.com/hanghee/v/5285808