#mysql ERROR 1820
 
````
ERROR 1820 (HY000): You must reset your password using ALTER USER statement before executing this statement.
````
```` 
mysql> show databases;
ERROR 1820 (HY000): You must SET PASSWORD before executing this statement
````
- MySQL 설치 후 첫 접속 시 다음과 같은 에러에 직면한다면

```` 
mysql> SET PASSWORD=PASSWORD('0000');
````
- 루트 (root) 암호 (password)를 설정해주어야 한다.