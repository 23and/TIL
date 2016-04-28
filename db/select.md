#select

###유틸
- sqlplus.exe만의 옵션 명령어
 - 검색데이터 view 조절
````
set linesize 200
set pagesize 200
````
- 오라클 DB의 잉여 table[dummy table]
 - table명 : dual
 - sql문장만으로 시스템 시간 검색 및 연산 작업 가능
 - 단, from절은 필수
 - select 2+3 from dual; // 이런 것도 된다.

###검색 select 문장 문법
- 기본 select
```` 
select절
from절
````
- 조건절이 있는 select
````
select절 검색컬럼명
from절 table명
where절 조건식;
````

- 정렬 검색
````
select절
from절
ordrer by절;
````

###예시
- emp table의 모든 내용 검색
````
select * from emp;
````

- 해당 계정이 보유한 table의 모든 종류 검색
````
select * from tab;
````

- 쓰레기 table 삭제
````
purge recyclebin;
````

- 부서의 정보 검색
````
select * from dept;
````

- SMITH 사원의 급여만 검색
 - 데이터는 대소문자 중요
````
select sal from emp where ename='SMITH';
````

- emp table의 구조
````
desc emp;
````

- emp table의 모든 사원의 입사일만 검색
````
select hiredate from emp;
````

- emp table의 모든 사원의 이름과, 사번 검색
````
select ename, empno from emp;
````

- 사번 검색시 검색된 헤더 부분의 empno가 아니라 '사번'이란 이름으로 검색
````
select empno as 사번 from emp;
select empno 사번 from emp;
````

- 사원명과 부서번호만 검색
````
select ename, deptno from emp;
````

- 부서번호만 검색 단 중복된 데이터 제거
 - distinct : 중복 제거 키워드
````
select distinct deptno from emp;
````

- 검색 데이터를 정렬 검색
````
select distinct deptno from emp;
select distinct deptno from emp order by deptno;
select distinct deptno from emp order by deptno desc;
select distinct deptno from emp order by deptno asc;
````

- hiredate도 날짜 형식임에도 정렬 가능
 - 경력자 순으로 이름, 입사일 검색
````
select ename, hiredate from emp order by hiredate;
select ename, hiredate from emp order by hiredate asc;
````

###연산식
- 순수 수학 연산 가능
````
select 3*2 from dual;
````

- emp table에서 모든 직원들의 연봉 계산
 - 단 comm은 미고려
````
select sal*12 as 연봉 from emp;
````

- emp table에서 comm까지 연봉에 합으로 계산
 - 단 comm이 null인 경우 연산식 적용해선 안됨
````
select empno, comm
from emp
where comm is not null;

select empno, comm
from emp
where comm is null;
````

- 연봉에 comm 포함한 검색(empno, 연봉)
````
select (sal*12)+comm from emp;	-- 논리적인 오류
select (sal*12)+comm from emp where comm is not null; // 논리적인 오류
````
 - 오라클 자체 지원 함수 
 - nvl(null값 컬럼명, 치환할 데이터) - null값을 다른 데이터로 치환
````
select (sal*12)+nvl(comm, 0) from emp;
````

- sal이 900이상(>=)인 사원들의 이름, 급여만 검색
````
select ename, sal from emp where sal >= 900;
````

- deptno가 10이고 job이 매니저인 사원의 이름 검색
 - and 연산식
````
select ename from emp where deptno = 10  and job = 'MANAGER';
````

-deptno가 10이면서 job이 매니저인 사원이름 검색
````
select ename, deptno, job from emp where deptno = 10 and job = 'MANAGER';
````

- deptno가 10이 아닌 모든 사원이름(ename), 부서번호(deptno) 검색
 - 부정 연산자 : not, !=, <>
````
select ename, deptno from emp where deptno != 10;
select ename, deptno from emp where deptno <> 10;
select ename, deptno from emp where not deptno = 10;
````

- sal이 2000이하이거나 3000이상인 사원명(ename) 검색
````
select ename, sal from emp where sal <= 2000 or sal >= 3000;
````

- comm이 300 or 500 or 1400인 사원명과 comm 검색
 - in 연산자(다중 데이터 검색)
````
select ename, comm from emp where comm = 300 or comm = 500 or comm = 1400;
select ename, comm from emp where comm in  (300, 500, 1400);
````

- comm이 300 or 500 or 1400들이 아닌 사원명과 comm 검색
````
select ename, comm from emp where comm not in (300, 500, 1400);
select ename, comm from emp where not comm in (300, 500, 1400);
````

- 81년도에 입사한 사원 이름 검색
 - between 비교값1 and 비교값2
 - 특정범위 설정 및 검색
 - yy/mm/dd 형식으로 날짜 출력 확인
````
select hiredate from emp where hiredate >= '81/01/01' and hiredate <= '81/12/31';
select hiredate from emp where hiredate between '81/01/01' and '81/12/31';
````
- like 연산자 : 한두 음절로 다수의 데이터 검색에 용이
 - like 연관 표기법 : %[철자개수 제한 없음], _[한음절 의미]
````
select ename from emp where ename like 'M%';
select ename from emp where ename like 'M_';
select ename from emp where ename like '_M%'; //SMITH 출력
````

- M음절이 포함된 모든 직원 이름
````
select ename from emp where ename like '%M%';
````