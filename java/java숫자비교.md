#java ���� ��
- int
 - Primitive �ڷ��� (long, float, double,. ....)
 - �ڷ���
 - ��� ������ ����. 
 - null �� �ʱ�ȭ �Ұ���, 0���� �ʱ�ȭ

- Integer 
 - Wrapper Ŭ����(��ü)
 - Ŭ����
 - Unboxing �� ���� ������ ��� ������ �Ұ���������, null���� ó���� �� ����.
 - null�� ó���� �����ؼ� SQL �� ������ ��� ó���� ����. �������� ��������� �Ұ��� 

- int�� Integer�� ��ȯ
````java
int i = integer.intValue();
Integer integer = new Integer(i);
````

- Boxing�� Unboxing �� ���� 
 - Boxing �ڷ��� : Wrapper Ŭ���� (Integer)
 - Unboxing �ڷ��� : Privimtive �ڷ���  (int)
 - int -> Integer �� ��ȯ (Auto boxing)
 - Integer -> int �� ��ȯ ( Auto unboxing)
 - Autoboxing�� �ڹ� �����Ϸ��� primitive���� Wrapper Ŭ���� ���̿��� ����� �ڵ� ��ȯ

````
###���� Ÿ�� ��
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

- �� ��� �� primitive type(int) �� ������ �ϳ��� �ִٸ�, == �����ڴ� ������ ���Ѵ�.
- Boxed primitive �Ǵ� Wrapper class(Integer) ���� �� �ϴ� ���, == �����ڴ� �� ��ü�� �ּ� ���� �� �ϰ� �ȴ�.
- �������� �񱳴� equal �޼ҵ带 ����ؾ��Ѵ�.
���� : marobiana.tistory.com, egloos.zum.com/hanghee/v/5285808