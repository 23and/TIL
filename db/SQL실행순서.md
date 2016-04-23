#SQL실행순서
- FROM -> WHERE -> GROUP BY -> HAVING -> SELECT -> ORDER BY
- SELECT절의 수행 순서가 FROM절이나 WHERE절 보다 늦기때문에 SELECT절에서 선언해 둔 별칭을 FROM이나 WHERE절에서 사용하면 알 수 없다.
- ORDER BY보다 SELECT를 먼저 수행하므로 SELECT에서 Fetch또는 가공한 컬럼값, 컬럼명칭 및 컬럼순서등이 ORDER BY를 수행하는 순간에는 이미 메모리에 전부 만들어져 있다.
- ORDER BY절에서는 SELECT절에서 가공한 컬럼명칭(별칭)을 사용할 수 있다.

````
SELECT ename, sal, comm, sal+comm AS total
FROM   emp
WHERE  comm is not null
ORDER BY total desc;
````

````
-FROM
 - emp라는 테이블에서 어떤값을 가져온다.
- WHERE
 - 조건이 comm값이 null이 아닌 것만 가져온다.
- SELECT 
 - ename,sal,comm,total값을 선택한다.
- ORDER BY
 - 보여줄 때 total값이 내림차순으로 정렬되게 해서 보여준다.
````

###그룹함수 
- 더하기 SUM
 - SELECT SUM(컬럼값) FROM Table명
- 평균 AVG
 - SELECT AVG(컬럼값) FROM Table명
- 최고값 MAX
 - SELECT MAX(컬럼값) FROM Table명
- 최소값 MIN
 - SELECT MIN(컬럼값) FROM Table명

- GROUP BY
 - Group By절은 언제 사용할까?
 - ex) 부서별 학년별 등 그룹으로 값을 뽑아와야할때 사용한다
 - 부서별로 연봉을 가져올 때
  - SELECT department_id, AVG(salary) FROM emp GROUP BY department_id;
 - GROUP BY절에서 사용할 수 있는 컬럼
  - 그룹 함수
  - GROUP BY에서 사용한 컬럼