#mysql string function

###left
- left(문자열, 끊어올 문자 개수)
````sql
select left('12345', 2)
````
````
12
````

###right
- right(문자열, 끊어올 문자 개수)
````sql
select right('12345', 2)
````
````
45
````

###substring_index
- SUBSTRING_INDEX(문자열, 찾는 문자열, 찾는 문자열의 순번)
````sql
select substring_index('123456abcd123456', '2', 2)
````
````
123456abcd1
````

###trim
- trim({leading | trailing | both} 바꾸고자 하는 문자열 from 문자열)
​ - both : 좌우로 모두 제거
 - leading : 좌측만 제거
 - trailing : 우측만 제거
````sql
trim(both '0' from '00012000567000')
````
````
12000567
````
````sql
trim(leading '0' from '00012000567000')
````
````
12000567000
````
````sql
trim(trailing '0' from '00012000567000')
````
````
00012000567
````

###replace
- 특정 Column의 값의 일부를 바꾸고 싶을 때
````sql
update table set column=replace(str,  find_string, replace_with)
````

###like
- 특정 문자가 포함되어 있는 데이터를 검색 할 때
- 특정 문자로 시작하는 데이터 검색
````sql
SELECT [필드명] FROM [테이블명] WHERE [필드명] LIKE '특정 문자열%;
````
- 특정 문자로 끝나는 데이터 검색
````
SELECT [필드명] FROM [테이블명] WHERE [필드명] LIKE '% 특정 문자열;
````
- 특정 문자 포함  데이터  검색
````
SELECT [필드명] FROM [테이블명] WHERE [필드명] LIKE '% 특정 문자열%;
````
