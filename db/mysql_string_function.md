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


