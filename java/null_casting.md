#null casting

````java
//컴파일, 런타임 에러 x
null == null
````

````java
//primitve type에 null -> 컴파일 에러
int a = null;
````

````java
//primitive boxing -> 런타임시 에러
Integer integer = null;
int a = (int) integer; // npe
int b = (Integer) null;  //npe
````

출처 : http://knight76.tistory.com/entry/%EC%9E%90%EB%B0%94-null-casting-%EC%A3%BC%EC%9D%98-%EC%82%AC%ED%95%AD