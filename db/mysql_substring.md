#mysql substring

````
substring_index( 대상문자, 구분자, 인덱스)
````
````
substring( 대상문자, 시작인덱스, 읽어들일 길이)
````
- sacn table -> code 컬럼 값의 마지막 3글자는 register table의 id값과 동일하다.
- code, id는 unique이다.
- code값을 통해 register table의 name 정보를 검색하기 위해 substring을 사용했다.
````
select name from scan, register where register.id = substring(scan.code, 9, 3);
````