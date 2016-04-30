#subQuery
- select문 내의 또다른 select
- 구조
```
mainQuery (subQuery)
````


###예시
- SMITH라는 직원 부서명 검색
````
select dname
from dept
where deptno = (select deptno 
		from emp
		where ename = 'SMITH');
```


- SMITH와 동일한 직급(job)을 가진 사원들 모든 정보 검색(SMITH 포함)
````
select *
from emp
where job = (select job from emp where ename = 'SMITH');
````


- SMITH와 급여가 동일하거나 더 많은(>=) 사원명과 급여 검색
````
select ename, sal from emp where sal >= (select sal from emp where ename = 'SMITH');
````


- DALLAS에 근무하는 사원의 이름, 부서번호 검색
````
select ename, deptno from emp where deptno = (select deptno from dept where loc = 'DALLAS');
````

- 평균 급여보다 더 많이 받는(>) 사원이름, 급여 검색
````
select ename, sal from emp where sal > (select avg(sal) from emp);
````


- 서브쿼리 결과가 다중행인 문장
- 급여가 3000 이상인 사원이 소속된 부서에 속한 사원이름, 급여 검색
````
select deptno from emp where sal >= 3000;
````


- 힌트 : or 연산자 여러 개의 효과 = in
````
select ename, sal from emp where deptno in (select deptno from emp where sal >= 3000);
````


- in 연산자를 이용하여 부서별로 가장 급여를 많이 받는 사원의 정보(사번, 사원명, 급여, 부서번호) 검색
````
select empno, ename, sal, deptno from emp where (sal, deptno) in (select max(sal), deptno from emp group by deptno);
````


- 직무가 MANAGER인 사람이 속한 부서의 부서번호와 부서명과 지역 검색
````
select deptno, dname, loc from dept where deptno in (select deptno from emp where job = 'MANAGER');
````