#subQuery
- select�� ���� �Ǵٸ� select
- ����
```
mainQuery (subQuery)
````


###����
- SMITH��� ���� �μ��� �˻�
````
select dname
from dept
where deptno = (select deptno 
		from emp
		where ename = 'SMITH');
```


- SMITH�� ������ ����(job)�� ���� ����� ��� ���� �˻�(SMITH ����)
````
select *
from emp
where job = (select job from emp where ename = 'SMITH');
````


- SMITH�� �޿��� �����ϰų� �� ����(>=) ������ �޿� �˻�
````
select ename, sal from emp where sal >= (select sal from emp where ename = 'SMITH');
````


- DALLAS�� �ٹ��ϴ� ����� �̸�, �μ���ȣ �˻�
````
select ename, deptno from emp where deptno = (select deptno from dept where loc = 'DALLAS');
````

- ��� �޿����� �� ���� �޴�(>) ����̸�, �޿� �˻�
````
select ename, sal from emp where sal > (select avg(sal) from emp);
````


- �������� ����� �������� ����
- �޿��� 3000 �̻��� ����� �Ҽӵ� �μ��� ���� ����̸�, �޿� �˻�
````
select deptno from emp where sal >= 3000;
````


- ��Ʈ : or ������ ���� ���� ȿ�� = in
````
select ename, sal from emp where deptno in (select deptno from emp where sal >= 3000);
````


- in �����ڸ� �̿��Ͽ� �μ����� ���� �޿��� ���� �޴� ����� ����(���, �����, �޿�, �μ���ȣ) �˻�
````
select empno, ename, sal, deptno from emp where (sal, deptno) in (select max(sal), deptno from emp group by deptno);
````


- ������ MANAGER�� ����� ���� �μ��� �μ���ȣ�� �μ���� ���� �˻�
````
select deptno, dname, loc from dept where deptno in (select deptno from emp where job = 'MANAGER');
````