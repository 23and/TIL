#java 대소문자 변환

````java
public class ConvertString {
  private static final int lowerStart = 97; //소문자 'a' 아스키 값
  private static final int lowerEnd     = 122;  //소문자 'x' 아스키 값
  private static final int upperStart   = 65; //대문자 'A' 아스키 값
  private static final int upperEnd     = 90; //대문자 'X' 아스키 값
  
  public static char convertUpperToLower(char s) {
    int i=s;
    if(i>=upperStart && i<=upperEnd) i = i+32;  //대문자인 경우 +32 하면 소문자로 변환
    return (char)i;
  }
  
  public static char convertLowerToUpper(char s) {
    int i=s;
    if(i>=lowerStart && i<=lowerEnd) i = i-32;  //소문자인 경우 -32 하면 소문자로 변환
    return (char)i;
  }
}
````

```java
String upper = "A";
String lower = "a";

upper .toLowerCase()); // String 형에서 제공되는 소문자 변환 함수
lower .toUpperCase()); // String 형에서 제공되는 대문자 변환 함수
````

````java
Character.toLowerCase('A'); // Charactor 형에서 제공되는 소문자 변환 함수
Character.toUpperCase('a'); // Charactor 형에서 제공되는 대문자 변환 함수
````