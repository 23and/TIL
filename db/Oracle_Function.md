#Oracle DB가 지원하는 내장 함수

###숫자 함수
- round(값[,반올림할자리수]) : 반올림 구하는 함수
````
select 34.5, round(34.5) from dual;
select 34.5, round(34.534,2) from dual;
select 34.5, round(34.536,2) from dual;
````

- abs() : 절대값 구하는 함수
````
select -10, abs(-10) from dual;
````

- trunc() : 지정한 자리수 이하 버리는 함수
 - 자릿수 데이터 표기 : + 실수 자리 의미, - 정수 자리 의미
````
select 34.5, trunc(34.534,2) from dual;
select 34.5, trunc(34.536,2) from dual;
select 34.5, trunc(34.536,-2) from dual;
select 346.5, trunc(346.536,-2) from dual;
````


- mod() : 나누고 난 나머지값 반환 함수
````
select mod(17, 3) from dual;
````


- emp table에서 사번이 홀수인 사원의 사원명과 사번 검색
````
select ename, empno from emp where mod(empno, 2) <> 0;
````


###문자함수
- upper() : 대문자화 하는 함수
 - 대문자 철자 : uppercase
 - 소문자 철자 : lowercase


- lower() : 소문자화 하는 함수
````
select upper('aBc'), lower('aBc') from dual;
````

- 'manager' 데이터로 뜻이 일치되는 job을 보유한 사원의 이름, 직무(job) 검색
````
select ename, job from emp where job = upper('manager');
select ename, job from emp where lower(job) = 'manager';
````


- length() : 문자열 길이 체크함수
````
select length('가나다'), length('abc') from dual;
````


- lengthb() : byte수 체크함수
````
select lengthb('가나다'), lengthb('abc') from dual;
````


- substr() : 문자열 일부 착출함수
````
select substr('abcdtest',2, 4) from dual;
````

- 년도 구분없이 2월에 입사한 사원이름, 입사일 검색
 - oracle의 date 타입에서 substr() 함수 사용 가능
````
select ename, hiredate from emp where substr(hiredate,4,2) = '02';
````


- trim() : 데이터 앞뒤의 잉여여백 제거 함수
 - ' abc '의 앞뒤 여백 제거 후 문자열 길이 검색
````
select length(trim(' abc ')) from dual;
````


###날짜 함수
- oracle db의 지원 속성 : sysdate 현시스템의 날짜값


- 어제, 오늘, 내일 날짜 검색
````
select sysdate-1 as 어제, sysdate 오늘, sysdate+1 내일 from dual;
````

- emp table의 근무일수 검색하기
````
select sysdate-hiredate from emp;
select round(sysdate-hiredate) from emp;
select trunc(sysdate-hiredate) from emp;
select from dual;
````


- 택배 물류회사 : 오늘 오전 11시 59분까지의 구매에 한해서만 오늘 날짜로
 - 주문으로 간주
 - 주문 날짜 검색의 sql 문장은 어떻게 작업해야 하나요?
````
select round(sysdate) 주문일 from dual;
````


- add_months() : 특정 개월수 더하는 함수
 - 6개월 이후의 날짜 검색
````
select add_months(hiredate, 6) from emp;
select add_months(sysdate, 6) from dual;
````


- months_between() : 두 날짜 사이의 개월수 검색
````
select months_between(sysdate, '2013-02-04') from dual;
select months_between(sysdate, '2014-11-04') from dual;
````


- next_day(기준일자, 검색기준요일) : 요일을 기준으로 특정 날짜 검색
````
select sysdate, next_day(sysdate, '토요일') from dual;
````


- last_day(날짜) 
````
select last_day('2014/02/03') from dual;
select last_day('2014/12/30') from dual;
````


###형변환 함수
- to_char() :  숫자를 문자형으로, 날짜를 문자형으로 변환
 - 날짜를 문자형으로 변환
 - 시분초 표기법 : hh = 12시 기준, hh24 = 24시간 기준
````
select sysdate from dual;
select to_char(sysdate, 'yyyy-mm-dd') from dual;
select to_char(sysdate, 'yyyy/mm/dd') from dual;

select to_char(sysdate, 'yyyy-mm-dd hh:mi:ss') from dual;
select to_char(sysdate, 'yyyy-mm-dd hh24:mi:ss') from dual;
select to_char(sysdate, 'yyyy-mm-dd hh24:mi:ss am') from dual;
````

- 숫자를 문자형으로 변환
 - 원단위 표시 : L or l [local]
 - 유효자리수 만큼만 편집 : 9라는 숫자 활용
 - 무효자리수 만큼 0으로 편집 : 0 숫자 활용
````
select to_char(1234, '9999.99') from dual;
select to_char(1234, '99999.99') from dual;
select to_char(1234, '$9999.99') from dual;
select to_char(1234, 'L9999.99') from dual;
select to_char(1234, 'L9999') from dual;
select to_char(1234, '00000') from dual;
````
- 오류[데이터손실] : select to_char(12345, '999.99') from dual;


- to_date() : 날짜 데이터로의 변환 함수
 - 오류 : select sysdate-20130101 from dual;
 - 오늘 대비 경과일수 검색
````
select sysdate-to_date(20141230, 'yyyy/mm/dd') from dual;
````


- emp 문자열로 date타입 검색 기능[data 타입의 검색시에는 날짜 포멧이 다양함]
 - 1980년 12월 17일 입사한 사원의 이름
````
select ename from emp where hiredate = '1980/12/17';
select ename from emp where hiredate = '1980-12-17';
````


- to_number() : 문자열을 숫자로 변환
 - '20,000'의 데이터에서 '10,000' 산술 연산하기
````
select to_number('20,000', '99,999') - to_number('10,000', '99,999') from dual;
````


###조건 함수
- decode() : 조건식 함수 if or switch와 흡사
 - decode(기준데이터 컬럼, 조건값1, 조건값1이 true인 경우 출력 데이터, 조건값2, 조건값2이 true인 경우 출력 데이터, 해당조건에 위배될 때 출력)
````
select deptno, decode(deptno, 10, 'A', 20, 'B', 30, 'C','무') from emp;
````


- emp table 월급여(sal) 인상 계산
 - job이 ANALYST인 경우 5% 인상, SALESMAN 10%, MANAGER 15%, CLERK 20%
````
select job, sal, decode(job, 'ANALYST', sal*1.05,
			     'SALESMAN', sal*1.1,
			     'MANAGER',sal*1.15,
			     'CLERK',sal*1.2
			) 연봉인상 from emp;

select empno, job, sal, decode(job, 'ANALYST, sal*1.05,
				    'SALESMAN', sal*1.1,
				    'MANAGER', sal*1.15,
				    'CLERK' sal*1.2,
				    sal) as 인상급여 from emp;
````
