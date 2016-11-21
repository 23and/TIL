#tomcat user
- conf/tomcat-user.xml
````
<tomcat-users>
	<role rolename="manager-gui"/>
	<user username="admin" password="admin" roles="manager-gui"/>
</tomcat-users>
````
- http://localhost:8080/manager
- user = "admin" and password = "admin"