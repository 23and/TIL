#split
- java.lang.String.split()
- public String[] split(String regex)
- public String[] split(String regex, int limit)
 - regex : 정규표현
 - limit : 분류할 문자열 수
- 문자열을 구분할 때 특정 구분자를 기준으로 나눠준다.
- 인수로 구분자가 넘어가며 데이터가 없어도 배열에 담아둔다.

````java
String str1 = "aa:bb:cc";
String str2 = "aa bb cc";

String[] result1 = str1.split(":"); // aa, bb, cc
String[] result2 = str2.split("\\s") // aa, bb, cc -> \s : 공백, \t : 탭
String[] result3 = str1.split(":", 2) //aa, bb:cc
````