#SQL�������
- FROM -> WHERE -> GROUP BY -> HAVING -> SELECT -> ORDER BY
- SELECT���� ���� ������ FROM���̳� WHERE�� ���� �ʱ⶧���� SELECT������ ������ �� ��Ī�� FROM�̳� WHERE������ ����ϸ� �� �� ����.
- ORDER BY���� SELECT�� ���� �����ϹǷ� SELECT���� Fetch�Ǵ� ������ �÷���, �÷���Ī �� �÷��������� ORDER BY�� �����ϴ� �������� �̹� �޸𸮿� ���� ������� �ִ�.
- ORDER BY�������� SELECT������ ������ �÷���Ī(��Ī)�� ����� �� �ִ�.

````
SELECT ename, sal, comm, sal+comm AS total
FROM   emp
WHERE  comm is not null
ORDER BY total desc;
````

````
-FROM
 - emp��� ���̺��� ����� �����´�.
- WHERE
 - ������ comm���� null�� �ƴ� �͸� �����´�.
- SELECT 
 - ename,sal,comm,total���� �����Ѵ�.
- ORDER BY
 - ������ �� total���� ������������ ���ĵǰ� �ؼ� �����ش�.
````

###�׷��Լ� 
- ���ϱ� SUM
 - SELECT SUM(�÷���) FROM Table��
- ��� AVG
 - SELECT AVG(�÷���) FROM Table��
- �ְ� MAX
 - SELECT MAX(�÷���) FROM Table��
- �ּҰ� MIN
 - SELECT MIN(�÷���) FROM Table��

- GROUP BY
 - Group By���� ���� ����ұ�?
 - ex) �μ��� �г⺰ �� �׷����� ���� �̾ƿ;��Ҷ� ����Ѵ�
 - �μ����� ������ ������ ��
  - SELECT department_id, AVG(salary) FROM emp GROUP BY department_id;
 - GROUP BY������ ����� �� �ִ� �÷�
  - �׷� �Լ�
  - GROUP BY���� ����� �÷�