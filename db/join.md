#join

###INNER JOIN
- 조인하는 테이블의 ON 절의 조건이 일치하는 데이터만 출력
````
SELECT
*
FROM table_a as a
INNER JOIN table_b as b
ON a.uid = b.uid
````
- a.uid와 b.uid 컬럼의 값이 일치하는 데이터만 출력
###OUTER JOIN (조인하는 테이블의 ON 절의 조건중 한쪽의 데이터를 모두 출력
````
SELECT
*
FROM table_a as a
LEFT OUTER JOIN table_b as b
ON a.uid = b.uid
````
- a.uid 컬럼이 존재하지만 b.uid 컬럼이 존재하지 않으면 b.uid 컬럼은 NULL로 출력
