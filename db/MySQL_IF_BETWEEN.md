#MySQL IF, BETWEEN

###IF
````
IF(조건, 'Yes', 'No')
````
- 조건이 참이면 Yes, 거짓이면 No 표시
- Null
 -'컬럼 IS NULL'
````
IFNULL(필드명, " 대체할 값")
````
or
````
IFNULL(필드명, IFNULL(필드명a, 필드명b)
````
###BETWEEN
````
SELECT A FROM TABLE
WHERE B BETWEEN VALUE1 AND VALUE2
````
- VALUNE 조건들을 포함하여 그 안에 데이터를 가져온다.
````
SELECT A FROM TABLE
WHERE B NOT BETWEEN VALUE1 AND VALUE2
````
- 반대