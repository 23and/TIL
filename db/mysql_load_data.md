#mysql load data

````sql 
load data infile
````
- mysqldㅔ서 탭 형식 문서를 테이브렝 직접 넣는 방법
- 탭 형식 txt문서 데이터를 insert into문을 사용하지 않고 바로 입력하는 방법
````sql
load data local infile "file경로" into table "table name";
load data local infile 'path' into table test;
````
- table name 뒤에 옵션
````sql
fields terminated by ',';
````
- 쉼표 형태로 칼럼을 구분한다
````sql
fields terminated by '';
````
- space 형태로 칼럼을 구분한다.
- 옵션이 없는 경우 기본적으로 tab 형식을 지원