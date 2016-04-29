#Oracle DB�� �����ϴ� ���� �Լ�

###���� �Լ�
- round(��[,�ݿø����ڸ���]) : �ݿø� ���ϴ� �Լ�
````
select 34.5, round(34.5) from dual;
select 34.5, round(34.534,2) from dual;
select 34.5, round(34.536,2) from dual;
````

- abs() : ���밪 ���ϴ� �Լ�
````
select -10, abs(-10) from dual;
````

- trunc() : ������ �ڸ��� ���� ������ �Լ�
 - �ڸ��� ������ ǥ�� : + �Ǽ� �ڸ� �ǹ�, - ���� �ڸ� �ǹ�
````
select 34.5, trunc(34.534,2) from dual;
select 34.5, trunc(34.536,2) from dual;
select 34.5, trunc(34.536,-2) from dual;
select 346.5, trunc(346.536,-2) from dual;
````


- mod() : ������ �� �������� ��ȯ �Լ�
````
select mod(17, 3) from dual;
````


- emp table���� ����� Ȧ���� ����� ������ ��� �˻�
````
select ename, empno from emp where mod(empno, 2) <> 0;
````


###�����Լ�
- upper() : �빮��ȭ �ϴ� �Լ�
 - �빮�� ö�� : uppercase
 - �ҹ��� ö�� : lowercase


- lower() : �ҹ���ȭ �ϴ� �Լ�
````
select upper('aBc'), lower('aBc') from dual;
````

- 'manager' �����ͷ� ���� ��ġ�Ǵ� job�� ������ ����� �̸�, ����(job) �˻�
````
select ename, job from emp where job = upper('manager');
select ename, job from emp where lower(job) = 'manager';
````


- length() : ���ڿ� ���� üũ�Լ�
````
select length('������'), length('abc') from dual;
````


- lengthb() : byte�� üũ�Լ�
````
select lengthb('������'), lengthb('abc') from dual;
````


- substr() : ���ڿ� �Ϻ� �����Լ�
````
select substr('abcdtest',2, 4) from dual;
````

- �⵵ ���о��� 2���� �Ի��� ����̸�, �Ի��� �˻�
 - oracle�� date Ÿ�Կ��� substr() �Լ� ��� ����
````
select ename, hiredate from emp where substr(hiredate,4,2) = '02';
````


- trim() : ������ �յ��� �׿����� ���� �Լ�
 - ' abc '�� �յ� ���� ���� �� ���ڿ� ���� �˻�
````
select length(trim(' abc ')) from dual;
````


###��¥ �Լ�
- oracle db�� ���� �Ӽ� : sysdate ���ý����� ��¥��


- ����, ����, ���� ��¥ �˻�
````
select sysdate-1 as ����, sysdate ����, sysdate+1 ���� from dual;
````

- emp table�� �ٹ��ϼ� �˻��ϱ�
````
select sysdate-hiredate from emp;
select round(sysdate-hiredate) from emp;
select trunc(sysdate-hiredate) from emp;
select from dual;
````


- �ù� ����ȸ�� : ���� ���� 11�� 59�б����� ���ſ� ���ؼ��� ���� ��¥��
 - �ֹ����� ����
 - �ֹ� ��¥ �˻��� sql ������ ��� �۾��ؾ� �ϳ���?
````
select round(sysdate) �ֹ��� from dual;
````


- add_months() : Ư�� ������ ���ϴ� �Լ�
 - 6���� ������ ��¥ �˻�
````
select add_months(hiredate, 6) from emp;
select add_months(sysdate, 6) from dual;
````


- months_between() : �� ��¥ ������ ������ �˻�
````
select months_between(sysdate, '2013-02-04') from dual;
select months_between(sysdate, '2014-11-04') from dual;
````


- next_day(��������, �˻����ؿ���) : ������ �������� Ư�� ��¥ �˻�
````
select sysdate, next_day(sysdate, '�����') from dual;
````


- last_day(��¥) 
````
select last_day('2014/02/03') from dual;
select last_day('2014/12/30') from dual;
````


###����ȯ �Լ�
- to_char() :  ���ڸ� ����������, ��¥�� ���������� ��ȯ
 - ��¥�� ���������� ��ȯ
 - �ú��� ǥ��� : hh = 12�� ����, hh24 = 24�ð� ����
````
select sysdate from dual;
select to_char(sysdate, 'yyyy-mm-dd') from dual;
select to_char(sysdate, 'yyyy/mm/dd') from dual;

select to_char(sysdate, 'yyyy-mm-dd hh:mi:ss') from dual;
select to_char(sysdate, 'yyyy-mm-dd hh24:mi:ss') from dual;
select to_char(sysdate, 'yyyy-mm-dd hh24:mi:ss am') from dual;
````

- ���ڸ� ���������� ��ȯ
 - ������ ǥ�� : L or l [local]
 - ��ȿ�ڸ��� ��ŭ�� ���� : 9��� ���� Ȱ��
 - ��ȿ�ڸ��� ��ŭ 0���� ���� : 0 ���� Ȱ��
````
select to_char(1234, '9999.99') from dual;
select to_char(1234, '99999.99') from dual;
select to_char(1234, '$9999.99') from dual;
select to_char(1234, 'L9999.99') from dual;
select to_char(1234, 'L9999') from dual;
select to_char(1234, '00000') from dual;
````
- ����[�����ͼս�] : select to_char(12345, '999.99') from dual;


- to_date() : ��¥ �����ͷ��� ��ȯ �Լ�
 - ���� : select sysdate-20130101 from dual;
 - ���� ��� ����ϼ� �˻�
````
select sysdate-to_date(20141230, 'yyyy/mm/dd') from dual;
````


- emp ���ڿ��� dateŸ�� �˻� ���[data Ÿ���� �˻��ÿ��� ��¥ ������ �پ���]
 - 1980�� 12�� 17�� �Ի��� ����� �̸�
````
select ename from emp where hiredate = '1980/12/17';
select ename from emp where hiredate = '1980-12-17';
````


- to_number() : ���ڿ��� ���ڷ� ��ȯ
 - '20,000'�� �����Ϳ��� '10,000' ��� �����ϱ�
````
select to_number('20,000', '99,999') - to_number('10,000', '99,999') from dual;
````


###���� �Լ�
- decode() : ���ǽ� �Լ� if or switch�� ���
 - decode(���ص����� �÷�, ���ǰ�1, ���ǰ�1�� true�� ��� ��� ������, ���ǰ�2, ���ǰ�2�� true�� ��� ��� ������, �ش����ǿ� ����� �� ���)
````
select deptno, decode(deptno, 10, 'A', 20, 'B', 30, 'C','��') from emp;
````


- emp table ���޿�(sal) �λ� ���
 - job�� ANALYST�� ��� 5% �λ�, SALESMAN 10%, MANAGER 15%, CLERK 20%
````
select job, sal, decode(job, 'ANALYST', sal*1.05,
			     'SALESMAN', sal*1.1,
			     'MANAGER',sal*1.15,
			     'CLERK',sal*1.2
			) �����λ� from emp;

select empno, job, sal, decode(job, 'ANALYST, sal*1.05,
				    'SALESMAN', sal*1.1,
				    'MANAGER', sal*1.15,
				    'CLERK' sal*1.2,
				    sal) as �λ�޿� from emp;
````
