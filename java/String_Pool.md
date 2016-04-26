#String Pool
- == �����ڴ� �ּҸ� ���Ѵ�.
- equals �޼ҵ�� ��ü �ȿ� �ִ� ���ڿ��� ���Ѵ�.

````java
String str1 = "java";
String str2 = "java";
````
- str1 == str2 // ture
- java�� ���ڿ��� ��ü�� �Ǿ��ִµ�, ��ü�� �ʹ� ���ٺ��� ���̴� ������ ����� �Ѵ�. �׷��� ���������� String Ǯ�� ������ �ִ�.
- String str1 = "java"; -> JVM�� String Ǯ�� �־�д�.
- �Ȱ��� ���ڿ��� �ٽ� ������ String str2 = "java"; �̹� ���ִ� �ּҸ� ��ȯ���ش�.
- Singleton���� ó��
- �׷��� str1�� str2�� ���� �ּҸ� ����Ų��.


````java
String str1 = new String("java");
String str2 = new String("java");
````
- str1 == str2 // false
- ==�� �޸𸮻� �ּҸ� ���Ѵ�. ���ο� ��ü�� �����߱� ������ �ٸ� �ּҰ��� ���´�.
- equals�� ���ؾ��Ѵ�.


````java
String str1 = reader.readLine();
String str2 = reader.readLine();
````
- str1 == str2 // false
- reader�� ���ؼ� �о�� ���̱� ������ StringǮ�� ��ϵ��� �ʴ´�.


````java
String str1 = new String("java").toString();
String str2 = new String("java").toString();
````
- str1 == str2 // false
- String�� toString() ���ϰ��� this;�̴�. new String("java");�� ���� ����� ���´�.


````java
String str1 = String.valueOf("java");
String str2 = String.valueOf("java");
````
- str1 == str2 // true
- String�� valueOf(Object o)�� o.toString()�� �����Ѵ�.
- "java".toString() "java"�� String Ǯ�� ��ϵȴ�.
- str2 "java"�� str1���� ��ϵ� Ǯ���� �����´�. 
- �ᱹ ���� �ν��Ͻ��̴�.


````java
String str1 = "ja" + "va";
String str2 = "java";
````
- str1 == str2 // true
- �ڹ� �����Ϸ��� String str1 = "ja" + "va";�� String str1 = "java"; �� �����Ѵ�.

````java
String str1 = "ja";
String str2 = str1 + "va";
str1 = str1 + "va";
````
- str1 == str2 // false
- + �� ����� �κп� string�� �ƴ϶� ������ ���� ����̴�.
- �ڹ� �����Ϸ��� �ڵ带 �����Ѵ�.
- String str2 = new StringBuilder().append(str1).append("va").toString(); ���� �ڵ尡 �ٲ��. 
- str1 = str1 + "va";�� ����������.


- ���� : http://iilii.egloos.com/4427484