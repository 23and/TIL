#String Pool
- == 연산자는 주소를 비교한다.
- equals 메소드는 객체 안에 있는 문자열을 비교한다.

````java
String str1 = "java";
String str2 = "java";
````
- str1 == str2 // ture
- java는 문자열이 객체로 되어있는데, 객체가 너무 많다보니 줄이는 역할을 해줘야 한다. 그래서 내부적으로 String 풀을 가지고 있다.
- String str1 = "java"; -> JVM이 String 풀에 넣어둔다.
- 똑같은 문자열이 다시 들어오면 String str2 = "java"; 이미 들어가있는 주소를 반환해준다.
- Singleton으로 처리
- 그래서 str1과 str2는 같은 주소를 가르킨다.


````java
String str1 = new String("java");
String str2 = new String("java");
````
- str1 == str2 // false
- ==는 메모리상 주소를 비교한다. 새로운 객체를 생성했기 때문에 다른 주소값을 갖는다.
- equals로 비교해야한다.


````java
String str1 = reader.readLine();
String str2 = reader.readLine();
````
- str1 == str2 // false
- reader를 통해서 읽어온 값이기 때문에 String풀에 등록되지 않는다.


````java
String str1 = new String("java").toString();
String str2 = new String("java").toString();
````
- str1 == str2 // false
- String의 toString() 리턴값은 this;이다. new String("java");와 같은 결과가 나온다.


````java
String str1 = String.valueOf("java");
String str2 = String.valueOf("java");
````
- str1 == str2 // true
- String의 valueOf(Object o)는 o.toString()을 리턴한다.
- "java".toString() "java"는 String 풀에 등록된다.
- str2 "java"는 str1에서 등록된 풀에서 가져온다. 
- 결국 같은 인스턴스이다.


````java
String str1 = "ja" + "va";
String str2 = "java";
````
- str1 == str2 // true
- 자바 컴파일러는 String str1 = "ja" + "va";를 String str1 = "java"; 로 변경한다.

````java
String str1 = "ja";
String str2 = str1 + "va";
str1 = str1 + "va";
````
- str1 == str2 // false
- + 로 연결된 부분에 string이 아니라 변수가 들어가는 경우이다.
- 자바 컴파일러가 코드를 변경한다.
- String str2 = new StringBuilder().append(str1).append("va").toString(); 으로 코드가 바뀐다. 
- str1 = str1 + "va";도 마찬가지다.


- 참고 : http://iilii.egloos.com/4427484