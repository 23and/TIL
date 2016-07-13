#MySQL DATE_FORMAT

- Oracle의 TO_CHAR과 같은 기능
````
DATE_FORMAT(now(), '%Y-%m-%d') // 2016-06-13
DATE_FORMAT(now(), '%Y-%M-%D') // 2016-June-13th
DATE_FORMAT(now(), '%H:%i:%s')  // 22:26:11  (24시간)
DATE_FORMAT(now(), '%h:%i:%s')  // 10:26:11 (12시간)
````