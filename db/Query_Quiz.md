#Query Quiz
- name, status 그룹핑
- status 값이 없는 경우에는 0이 나올 수 있도록 하기
````
create table test (
	testid INT(100) UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
    name varchar(50) NULL
);
create table delivery (
     devid INT(100) UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
     status varchar(50) NULL,
     testid INT(100)
);
````
````
SELECT test.name, a.status, COALESCE(total, 0) AS total

FROM test,

     ( SELECT testid, status
     FROM 
          ( SELECT distinct testid FROM delivery ) aa,
          ( SELECT distinct status FROM delivery ) bb
     ) AS a

     LEFT OUTER JOIN

     ( SELECT testid, status, count(status) AS total
     FROM delivery
     GROUP BY testid, status ) AS b

     ON a.testid = b.testid and a.status = b.status

WHERE test.testid = a.testid

ORDER BY a.testid, a.status
````
````
+--------+-----------+-------+
| name   | status    | total |
+--------+-----------+-------+
| aaa   | 준비    	|     4 |
| aaa   | 완료       |     2 |
| aaa   | 시작       |     3 |
| bbb   | 준비    	|     0 |
| bbb   | 완료      	|     2 |
| bbb   | 시작      	|     3 |
| ccc   | 준비    	|     4 |
| ccc   | 완료      	|     0 |
| ccc   | 시작      	|     0 |
+--------+-----------+-------+
````