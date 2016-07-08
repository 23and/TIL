#MySQL 계정 추가

- root 계정 접속
````
mysql -uroot -p암호
````
or
````
mysql -uroot
````
- 데이터베이스 생성
````
create table db명;
````
- 데이터베이스 확인
````
show databases;
````
- GRANT를 이용하여 계정 추가
 - grant 권한종류(컬럼) on 대상 to 사용자계정 identified by 비밀번호[with grant option];
 - identified by 생략가능하다. 비밀번호를 지정하지 않으면 비밀번호 없이 접속된다.
 - with grant option 연대권한이 주어진다. a라는 유저에게 권한을 주면 a가 만든 계정들도 모두 해당 권한을 받는다.
 - *.* : 서버의 모든 데이터베이스, 모든 테이블
 - db명.* : 특정 데이터베이스의 모든 내용
 - db명.table명 : 특정 테이블
 - 사용자 계정 : 사용자의 계정과 호스트 이름으로 구성되고 이에 대한 접속 권한 부여
 - 사용자 계정은 mysql 접속시 지정하는 이름
````
grant all privileges on db명.* to ‘새로운계정’@localhost identified by ‘비밀번호’;
````
or
````
grant all privileges on *.* to '새로운계정'@'localhost' identified by ‘비밀번호’ with grant option;
grant all privileges on *.* to '새로운계정'@'%' identified by ‘비밀번호’ with grant option;
````
- user1사용자에게 0000비밀번호를 설정하고, localhost로 mysql서버에 접속할 수 있는 권한을 준다. user1은 db1데이터베이스의 모든 테이블에 대한 모든 권한을 수행할 수 있다.
````
grant all on db1.* to user1@localhost identified by ’0000’;
````
- 호스트 상관없이 user1사용자는 어디서나 서버에 접속할 수 있다.
````
grant select, insert, delete, update on db1.* to user1@‘%’ identified by ‘0000’;
````
- 특정 Database에 권한이 있는 계정 추가
````
grant all privileges on dbname.* to '새로운계정'@'localhost' identified by '암호' with grant option;
grant all privileges on dbname.* to '새로운계정'@'%' identified by '암호' with grant option;
````
- 계정 설정 후 적용
 - 변경된 내용을 재적용하여 서버에 통보
````
flush privileges;
````
- 접속
````
mysql -u 계정 -p db명
비밀번호 입력
````
or
````
mysql -u 계정 -p
비밀번호 입력
use db명
````
- 계정삭제
 - root계정 접속
````
drop user 계정명@호스트;
````

- 참고 http://blog.naver.com/meigoya/220643547300