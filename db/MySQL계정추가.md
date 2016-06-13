#MySQL 계정 추가

- root 계정 접속
````
mysql -uroot -p암호
````

- GRANT를 이용하여 계정 추가
````
grant all privileges on *.* to '새로운계정'@'localhost' identified by '암호' with grant option;
rant all privileges on *.* to '새로운계정'@'%' identified by '암호' with grant option;
````
- 특정 Database에 권한이 있는 계정 추가
````
grant all privileges on dbname.* to '새로운계정'@'localhost' identified by '암호' with grant option;
grant all privileges on dbname.* to '새로운계정'@'%' identified by '암호' with grant option;
````