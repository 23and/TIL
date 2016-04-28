#select

###��ƿ
- sqlplus.exe���� �ɼ� ��ɾ�
 - �˻������� view ����
````
set linesize 200
set pagesize 200
````
- ����Ŭ DB�� �׿� table[dummy table]
 - table�� : dual
 - sql���常���� �ý��� �ð� �˻� �� ���� �۾� ����
 - ��, from���� �ʼ�
 - select 2+3 from dual; // �̷� �͵� �ȴ�.

###�˻� select ���� ����
- �⺻ select
```` 
select��
from��
````
- �������� �ִ� select
````
select�� �˻��÷���
from�� table��
where�� ���ǽ�;
````

- ���� �˻�
````
select��
from��
ordrer by��;
````

###����
- emp table�� ��� ���� �˻�
````
select * from emp;
````

- �ش� ������ ������ table�� ��� ���� �˻�
````
select * from tab;
````

- ������ table ����
````
purge recyclebin;
````

- �μ��� ���� �˻�
````
select * from dept;
````

- SMITH ����� �޿��� �˻�
 - �����ʹ� ��ҹ��� �߿�
````
select sal from emp where ename='SMITH';
````

- emp table�� ����
````
desc emp;
````

- emp table�� ��� ����� �Ի��ϸ� �˻�
````
select hiredate from emp;
````

- emp table�� ��� ����� �̸���, ��� �˻�
````
select ename, empno from emp;
````

- ��� �˻��� �˻��� ��� �κ��� empno�� �ƴ϶� '���'�̶� �̸����� �˻�
````
select empno as ��� from emp;
select empno ��� from emp;
````

- ������ �μ���ȣ�� �˻�
````
select ename, deptno from emp;
````

- �μ���ȣ�� �˻� �� �ߺ��� ������ ����
 - distinct : �ߺ� ���� Ű����
````
select distinct deptno from emp;
````

- �˻� �����͸� ���� �˻�
````
select distinct deptno from emp;
select distinct deptno from emp order by deptno;
select distinct deptno from emp order by deptno desc;
select distinct deptno from emp order by deptno asc;
````

- hiredate�� ��¥ �����ӿ��� ���� ����
 - ����� ������ �̸�, �Ի��� �˻�
````
select ename, hiredate from emp order by hiredate;
select ename, hiredate from emp order by hiredate asc;
````

###�����
- ���� ���� ���� ����
````
select 3*2 from dual;
````

- emp table���� ��� �������� ���� ���
 - �� comm�� �̰��
````
select sal*12 as ���� from emp;
````

- emp table���� comm���� ������ ������ ���
 - �� comm�� null�� ��� ����� �����ؼ� �ȵ�
````
select empno, comm
from emp
where comm is not null;

select empno, comm
from emp
where comm is null;
````

- ������ comm ������ �˻�(empno, ����)
````
select (sal*12)+comm from emp;	-- ������ ����
select (sal*12)+comm from emp where comm is not null; // ������ ����
````
 - ����Ŭ ��ü ���� �Լ� 
 - nvl(null�� �÷���, ġȯ�� ������) - null���� �ٸ� �����ͷ� ġȯ
````
select (sal*12)+nvl(comm, 0) from emp;
````

- sal�� 900�̻�(>=)�� ������� �̸�, �޿��� �˻�
````
select ename, sal from emp where sal >= 900;
````

- deptno�� 10�̰� job�� �Ŵ����� ����� �̸� �˻�
 - and �����
````
select ename from emp where deptno = 10  and job = 'MANAGER';
````

-deptno�� 10�̸鼭 job�� �Ŵ����� ����̸� �˻�
````
select ename, deptno, job from emp where deptno = 10 and job = 'MANAGER';
````

- deptno�� 10�� �ƴ� ��� ����̸�(ename), �μ���ȣ(deptno) �˻�
 - ���� ������ : not, !=, <>
````
select ename, deptno from emp where deptno != 10;
select ename, deptno from emp where deptno <> 10;
select ename, deptno from emp where not deptno = 10;
````

- sal�� 2000�����̰ų� 3000�̻��� �����(ename) �˻�
````
select ename, sal from emp where sal <= 2000 or sal >= 3000;
````

- comm�� 300 or 500 or 1400�� ������ comm �˻�
 - in ������(���� ������ �˻�)
````
select ename, comm from emp where comm = 300 or comm = 500 or comm = 1400;
select ename, comm from emp where comm in  (300, 500, 1400);
````

- comm�� 300 or 500 or 1400���� �ƴ� ������ comm �˻�
````
select ename, comm from emp where comm not in (300, 500, 1400);
select ename, comm from emp where not comm in (300, 500, 1400);
````

- 81�⵵�� �Ի��� ��� �̸� �˻�
 - between �񱳰�1 and �񱳰�2
 - Ư������ ���� �� �˻�
 - yy/mm/dd �������� ��¥ ��� Ȯ��
````
select hiredate from emp where hiredate >= '81/01/01' and hiredate <= '81/12/31';
select hiredate from emp where hiredate between '81/01/01' and '81/12/31';
````
- like ������ : �ѵ� ������ �ټ��� ������ �˻��� ����
 - like ���� ǥ��� : %[ö�ڰ��� ���� ����], _[������ �ǹ�]
````
select ename from emp where ename like 'M%';
select ename from emp where ename like 'M_';
select ename from emp where ename like '_M%'; //SMITH ���
````

- M������ ���Ե� ��� ���� �̸�
````
select ename from emp where ename like '%M%';
````