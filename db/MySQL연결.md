#MySQL 연동

- MySQL connector
 - http://dev.mysql.com/downloads/connector/j/
 - mysql-connector-java-5.1.39-bin.jar
- Tomcat/lib에 connector.jar 추가
 - or JAVA_HOME/jre/lib/ext
- context.xml
 - maxActive: 최대 연결 가능한 Connection 숫자
 - maxIdle: Connection pool 유지를 위해 최대 대기 connection 숫자
 - maxWait: Connection 재 사용을 위해 대기해야 하는 최대 시간
````
<?xml version="1.0" encoding="UTF-8"?>
<Context>
	<Resource name="jdbc/mysql" 
			auth="Container"
              type="javax.sql.DataSource" 
              driverClassName="com.mysql.jdbc.Driver"
              url="jdbc:mysql://localhost:3306/db명?autoReconnect=true"
              username="계정 이름" password="계정 비밀번호" 
              maxActive="20"버
              maxIdle="10"
              maxWait="-1"/> 
</Context>
````
````
Context initContext = new InitialContext();
Context envContext = (Context) initContext.lookup("java:/comp/env");
source = (DataSource) envContext.lookup("jdbc/mysql");
````

