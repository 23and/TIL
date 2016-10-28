#LEFT
- table 필드가 text, Longtext인 경우에 레코드의 리스트를 구하는 경우
 -  해당 필드 전체 값을 가지고 올때 퍼포먼스 저하를 발생시킬 수 있다.
- 리스트에서 필드 전체를 가져오지 않을 경우 LEFT 함수를 쓸 수 있다.
````
LEFT(필드명, 길이)
````
````sql
SELECT LEFT(content, 50) from board;
````