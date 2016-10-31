#Shutdown the Spring boot
- pom.xml
````
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
````
- application.properties
````
endpoints.shutdown.enabled=true
````
- post to url
````
http://localhost:port/shutdown
````
