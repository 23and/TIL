#MySQL CONCAT

- CONCAT ( expr, expr )
- 문자열 expr과 expr를 연결하여 반환하며, 결과 문자열의 타입은 인수의 문자열에 의존한다.
- Oracle에서 CONCAT 함수는 오직 2개의 값만을 연결할 수 있다.
 - concat을 2번 사용 가능
 -|| 을 사용 가능
````
WHERE MEMBER LIKE CONCAT(CONCAT('%',?),'%') 
WHERE MEMBER LIKE  '%'||?||'%'
````
- kim이 들어가는 name 찾기
````
SELECT * FROM MEMBER WHERE NAME LIKE CONCAT('%', "kim", '%')
````