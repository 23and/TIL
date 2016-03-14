#DDL.sql
- table 생성(create)과 삭제(drop), 수정(alter)
- DDL(Data Definition Language)
- Oracle타입 : 자바 타입
 - varchar2(가변적인 메모리), char(고정메모리) : String
 - number(전체자리수[, 소수점이하자리]) : 정수, 실수
 - date : java.util.Date, java.sql.Date, String
- **tip** : 현업[필드,실무]에서는 date타입을 String으로 사용 빈도 높다

###table삭제 명령어
drop table kodb;
create table kodb(
	id varchar2(10),
	age number(3)
);
desc kodb;
select * from kodb;


###name(varchar2), age(number3) 칼럼 보유한 people table 생성
/* create table table명(
	칼럼명1 칼럼타입[(사이즈)] [제약조건] ,
	칼럼명2....
    ); */ 

drop table people;
create table people(
	name varchar2(20),
	age number(3)
);


###서브 쿼리 활용해서 table 생성(이미 존재하는 table기반으로 생성)
- emp table의 모든 데이터로 emp01 생성

drop table emp01;
create table emp01 as select * from emp;
desc emp01;
select * from emp01;


###서브쿼리 활용해서 특정 칼럼만으로 table 생성
- empno만으로 table 생성

create table emp02 as select empno from emp;
desc emp02;
select * from emp02;


###조건문 반영해서 table 생성
- emp table에서 deptno=10인 데이터들만 emp01로 복사하기

drop table emp01;
create table emp01 as select * from emp where deptno=10;
select * from emp01;


###table 구조로만 새로운 table생성시 사용되는 조건식 
- 절대 데이터 복사는 불가
- 조건식에 false인 데이터 비교시 적용되는 메카니즘 

drop table emp01;
create table emp01 as select * from emp where 1=0;
select * from emp01;

###table 수정 : alter
- job이라는 특정 칼럼 추가(job varchar2(10))
- 이미 데이터를 보유한 table에 새로운 job칼럼 추가 가능 

desc emp01;
drop table emp01;
create table emp01 as select empno, ename from emp;
desc emp01;

- job 컬럼 추가
alter table emp01 add(job varchar2(10));
desc emp01;


###이미 존재하는 칼럼 변경
desc emp01;
alter table emp01 modify(job varchar2(20));
desc emp01;


###이미 데이터가 존재할 경우 칼럼 사이즈 큰 사이즈로 변경 가능 
- 혹 사이즈 감소시 주의사항 : 이미 존재하는 데이터보다 적은 사이즈로 변경 절대 불가 

drop table emp01;
create table emp01 as select empno, ename, job from emp;
select * from emp01;
desc emp01;

alter table emp01 modify(job varchar(30));
desc emp01;
select * from emp01;

alter table emp01 modify(job varchar(10));
select * from emp01;

- 오류 : job이 보유하고 있는 데이터 사이즈가 5byte 큰 데이터가 존재할 경우 데이터 손실 방지를 위한 oracle의 정책 
- alter table emp01 modify(job varchar(5));


###칼럼 삭제 
- 데이터 존재시에도 자동 삭제 

alter table emp01 drop column job;
desc emp01;

###table 이름 변경
- emp01 table명을 kodb1로 변경

rename emp01 to kodb1;
desc emp01;
desc kodb1;

###table의 순수 데이터만 완벽하게 삭제하는 명령어 
- commit 불필요









