#spring boot jsp
- maven
- spring-boot-starter-web 포함 tomcat은 JSP 엔진을 포함하지 않는다.
````
<dependency>
	<groupId>org.apache.tomcat.embed</groupId>
    <artifactId>tomcat-embed-jasper</artifactId>
	<scope>provided</scope>
</dependency>
<dependency>
	<groupId>javax.servlet</groupId>
	<artifactId>jstl</artifactId>
</dependency>
````
- location
````
 /src/main/webapp/WEB-INF/jsp/xx.jsp 
````
- application.properties
````
spring.mvc.view.prefix=/WEB-INF/jsp/
spring.mvc.view.suffix=.jsp
````
