#security

````java
protected void configure(HttpSecurity http) throws Exception {
        http
                .authorizeRequests()
                        .anyRequest().authenticated()
                        .and()
                .formLogin()
                        .and()
                .httpBasic();
}
````
- 사용자 인증이 된 요청에 대해서만 요청을 허용한다.
- 사용자는 폼기반 로그인으로 인증 할 수 있다
- 사용자는 HTTP기반 인증으로 인증 할 수 있다.

````java
protected void configure(HttpSecurity http) throws Exception {
        http
                .authorizeRequests()
                        .anyRequest().authenticated()
                        .and()
                .formLogin()
                        .loginPage("/login")
                        .permitAll();
}
````
- loginPage("/login") 로그인 페이지의 위치를 명시한다.
- 모든 사용자들에게 접속을 허용하는 로그인페이지 “formLogin().permmitAll()” 메소드는 폼 기반 로그인과 관련된 모든 URL에 대한 모든 사용자의 접근 권한을 허용한다.

````html
<c:url value="/login" var="loginUrl"/>
<form action="${loginUrl}" method="post">       
	<c:if test="${param.error != null}">        
		<p>
			Invalid username and password.
		</p>
	</c:if>
	<c:if test="${param.logout != null}">       
		<p>
			You have been logged out.
		</p>
	</c:if>
	<p>
		<label for="username">Username</label>
		<input type="text" id="username" name="username"/>	
	</p>
	<p>
		<label for="password">Password</label>
		<input type="password" id="password" name="password"/>	
	</p>
	<input type="hidden" name="${_csrf.parameterName}" value="${_csrf.token}"/>
	<sec:csrfInput />
	<button type="submit" class="btn">Log in</button>
</form>

````