#UNION, UNION ALL

- UNION, UNION ALL은 둘 다 구조가 같은 데이터 행을 더해서 보여주는 기능을 가지고 있다. 
 - UNION은 unique한 레코드만 보여준다.
 - UNION ALL은 중복 데이터도 같이 보여준다. 

- ID 가 5인 사람이 한 명만 있다고 할 때, 위의 쿼리에서는 행이 하나 보여진다. 
````
SELECT * FROM EMPLOYEE WHERE ID = 5
UNION 
SELECT * FROM EMPLOYEE WHERE ID = 5
````

- UNION ALL의 실행 결과로는 똑같은 중복 행이 두 개 나온다.
````
SELECT * FROM EMPLOYEE WHERE ID = 5
UNION ALL
SELECT * FROM EMPLOYEE WHERE ID = 5
````

- 출처 : https://crack-tech-interview.com/page/4/