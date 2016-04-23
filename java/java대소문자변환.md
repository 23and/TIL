#java ��ҹ��� ��ȯ

````java
public class ConvertString {
  private static final int lowerStart = 97; //�ҹ��� 'a' �ƽ�Ű ��
  private static final int lowerEnd     = 122;  //�ҹ��� 'x' �ƽ�Ű ��
  private static final int upperStart   = 65; //�빮�� 'A' �ƽ�Ű ��
  private static final int upperEnd     = 90; //�빮�� 'X' �ƽ�Ű ��
  
  public static char convertUpperToLower(char s) {
    int i=s;
    if(i>=upperStart && i<=upperEnd) i = i+32;  //�빮���� ��� +32 �ϸ� �ҹ��ڷ� ��ȯ
    return (char)i;
  }
  
  public static char convertLowerToUpper(char s) {
    int i=s;
    if(i>=lowerStart && i<=lowerEnd) i = i-32;  //�ҹ����� ��� -32 �ϸ� �ҹ��ڷ� ��ȯ
    return (char)i;
  }
}
````

```java
String upper = "A";
String lower = "a";

upper .toLowerCase()); // String ������ �����Ǵ� �ҹ��� ��ȯ �Լ�
lower .toUpperCase()); // String ������ �����Ǵ� �빮�� ��ȯ �Լ�
````

````java
Character.toLowerCase('A'); // Charactor ������ �����Ǵ� �ҹ��� ��ȯ �Լ�
Character.toUpperCase('a'); // Charactor ������ �����Ǵ� �빮�� ��ȯ �Լ�
````